# Normal and Enterprise Modes for Clusters

You can configure your cluster for monitoring in one of the following ways:

- Using the configure_ifs.sh shell script that comes with Netwrix Auditor. See the [Configure Dell Isilon/PowerScale Cluster in Normal or Enterprise Mode via Shell Script](#configure-dell-isilonpowerscale-cluster-in-normal-or-enterprise-mode-via-shell-script) topic for additional information.
- Manual configuration. See the [Configure Dell Isilon/PowerScale Cluster in Normal or Enterprise Mode Manually](#configure-dell-isilonpowerscale-cluster-in-normal-or-enterprise-mode-manually) topic for additional information.

## Configure Dell Isilon/PowerScale Cluster in Normal or Enterprise Mode via Shell Script

Follow the steps to configure Dell Isilon/PowerScale cluster in Normal or Enterprise mode using shell script:

__Step 1 –__ On the computer where Auditor Server resides, navigate to _C:\Program Files (x86)\Netwrix Auditor\File Server Auditing_ and copy the configure_ifs.sh shell script to _/ifs/data_ catalog on your cluster.

__Step 2 –__ Navigate to your cluster command prompt through the SSH connection.

__Step 3 –__ Log in to your cluster as a root user.

__Step 4 –__ Run the shell script by executing the following command:

```
sh /ifs/data/configure_ifs.sh -z zone1 -a 1
```

where

```zone1``` is the name of the audited access zone on your file server.

```1``` is a combination of the bitwise flags. The table below shows the example combination of 4 flags:

|  |  |
| --- | --- |
| ```Successful changes``` | ```1``` |
| ```Failed change attempts``` | ```2``` |
| ```Successful reads``` | ```4``` |
| ```Failed read attempts``` | ```8``` |
| ```Total:``` | ```15``` |

## Configure Dell Isilon/PowerScale Cluster in Normal or Enterprise Mode Manually

Follow the steps to configure Dell Isilon/PowerScale cluster in Normal or Enterprise mode manually:

__Step 1 –__ Navigate to your cluster command prompt through the SSH connection.

__Step 2 –__ Log in to your cluster as a root user.

__Step 3 –__ Grant full access to the catalog _/ifs/.ifsvar/audit/_ for BUILTIN\Administrators:

```
chmod -R +a group "BUILTIN\Administrators" allow dir_gen_all,object_inherit,container_inherit, inherited /ifs/.ifsvar/audit/  
chmod -a group "BUILTIN\Administrators" allow dir_gen_all,object_inherit,container_inherit, inherited /ifs/.ifsvar/audit/  
chmod +a group "BUILTIN\Administrators" allow dir_gen_all,object_inherit,container_inherit /ifs/.ifsvar/audit/  
chmod +a user root allow dir_gen_read /ifs/.ifsvar/audit/
```

__Step 4 –__ Create a shared folder named netwrix_audit$ on a system zone. This folder points to _/ifs/.ifsvar/audit/_:

```
/usr/likewise/bin/lwnet share add "netwrix_audit$"="c:\\ifs\\.ifsvar\\audit\\"  
isi smb shares modify netwrix_audit$ --new-zone=system
```

Starting from Dell Isilon/PowerScale 9.2.0 and above, the ```lwnet``` command is considered as deprecated. When configuring audit manually, you see the following warning:

WARNING: lwnet has been deprecated.

Please use `isi smb ...` equivalents instead.

See `isi smb --help` for more information.

This command is required to create a shared folder pointed to _/ifs/.ifsvar/audit/_. Please ignore the warning.

__Step 5 –__ Add the BUILTIN\Administrators group in the share permissions for the netwrix_audit$ folder with _"full access"_ rights:

```
isi smb shares permission create --share=netwrix_audit$ --group="BUILTIN\Administrators"   
--permission-type=allow --permission=full --zone=system
```

__NOTE:__ Please verify the correctness of the path to the Isilon audit log files in "_Monitoring Plans -> `<MP name>` -> `<Isilon item name>` -> Edit item -> General -> File share UNC path to audit logs_"

It must follow the format:

```
\\<FQDN, NETBIOS, or IP for Isilon "system" zone>\netwrix_audit$\logs
```

__Step 6 –__ Enable protocol auditing for a selected zone (for example, _"zone1"_). Do one of the following, depending on your Dell Isilon/PowerScale storage version:

| Dell Isilon/PowerScale 7.x | Dell Isilon/PowerScale 8.x |
| --- | --- |
| ``` isi audit settings modify --add-audited-zones=zone1    --protocol -auditing-enabled=true ``` | ``` isi audit settings global modify --add-audited-zones=zone1    --protocol -auditing-enabled=true ``` |

Enable filters for auditing protocol operations that succeeded / failed for audited access zones on your cluster.

| Dell Isilon/PowerScale 7.x | Dell Isilon/PowerScale 8.2 and above |
| --- | --- |
| Successful changes |  |
| ``` isi zone zones modify zone1 --audit-success   =write,delete,set_security,rename ``` | ``` isi audit settings modify --zone=zone1 --audit-success   =write,delete,set_security,rename, create ``` |
| Failed change attempts |  |
| ``` isi zone zones modify zone1 --audit-failure   =create,write,delete,set_security,rename ``` | ``` isi audit settings modify --zone=zone1 --audit-failure   =create,write,delete,set_security,rename,open ``` |
| Successful reads |  |
| ``` isi zone zones modify zone1 --audit-success=read ``` | ``` isi audit settings modify --zone=zone1 --audit-success=read ``` |
| Failed read attempts |  |
| ``` isi zone zones modify zone1    --audit-failure= create,read ``` | ``` isi audit settings modify --zone=zone1    --audit-failure=create,read, open ``` |

__Step 7 –__ Create the _"netwrix_audit"_ role in your access zone (for example, "zone1") and add the required privileges to this role:

```
isi auth roles create --name=netwrix_audit --zone=zone1  
isi auth roles modify netwrix_audit --add-priv-ro="ISI_PRIV_LOGIN_PAPI,ISI_PRIV_AUTH,ISI_PRIV_AUDIT, ISI_PRIV_IFS_BACKUP" --zone=zone1  
isi auth roles modify netwrix_audit --add-group="BUILTIN\Administrators" --zone=zone1
```

## Considerations and Recommendations

When preparing to audit your Dell Isilon/PowerScale storage system, consider the following:

- If you plan to configure audit settings for Dell Isilon/PowerScale storage below the version 8.2 manually (without using the__configure_ifs.sh__ script), make sure that auditing of the ```success create``` events is __disabled__.

  For Dell Isilon/PowerScale storage below the version 8.2, the storage system logging will become too verbose, which may lead to data collector overload with excessive events, decrease its performance and result in data collection errors with the "_Timeout expired_" message issued.

  For Dell Isilon/PowerScale storage 8.2 and above, this option for manual audit configuration can be safely enabled.
- Auditing of the _System_ zone is not supported. As stated by Dell, this zone should be reserved for configuration access only. Current data should be stored in other access zones. See the [Isilon OneFS 8.2.1 CLI Administration Guide](https://www.dellemc.com/en-us/collaterals/unauth/technical-guides-support-information/2019/09/docu95372.pdf) topic for additional information.
