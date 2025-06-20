# Enable Auditing for Dell PowerStore

Follow the steps to enable auditing on Dell PowerStore.

- [Create an Event Publishing Pool](#create-an-event-publishing-pool)
- [Create an Event Publisher](#create-an-event-publisher)
- [Enable Event Publishing for the NAS Server](#enable-event-publishing-for-the-nas-server) OR
  [Enable or Disable Event Publishing for File System](#enable-or-disable-event-publishing-for-file-system)

See the
[Dell PowerStore - File Capabilities](https://www.delltechnologies.com/asset/en-us/products/storage/industry-market/h18155-dell-powerstore-file-capabilities.pdf)
white paper for additional information.

## Create an Event Publishing Pool

Follow the steps tTo create a new event publishing pool.:

**Step 1 –** Select **Storage** > **NAS Servers** > **NAS Settings** > **Publishing Pools**.

**Step 2 –** Click **Create** and specify the name of the pool.

**Step 3 –** Specify CEE's address or addresses.

![Create Event Publishing Pool](/img/versioned_docs/activitymonitor_7.1/config/dellpowerstore/eventpublishingpool.webp)

- For SMB shares monitoring (CIFS) enable following Post-Events: –

  - CloseModified
  - CloseUnmodified
  - CreateDir
  - CreateFile
  - DeleteDir
  - DeleteFile
  - OpenFileNoAccess
  - RenameDir
  - RenameFile
  - SetAclDir
  - SetAclFile

- For NFS exports monitoring enable following Post-Events: –

  - CloseModified,
  - CloseUnmodified
  - CreateDir
  - CreateFile
  - DeleteDir
  - DeleteFile
  - FileRead
  - FileWrite
  - OpenFileNoAccess
  - RenameDir
  - RenameFile
  - SetAclDir
  - SetAclFile
  - SetSecDir
  - SetSecFile

**Step 4 –** Click **Apply**.

## Create an Event Publisher

Follow the steps tTo create a an event publisher.:

**Step 1 –** Select **Storage** > **NAS Servers** > **NAS Settings** > **Events Publishers**.

![Events Publishing](/img/versioned_docs/activitymonitor_7.1/config/dellpowerstore/nasservers.webp)

**Step 2 –** Click **Create**.

![publishingpools](/img/versioned_docs/activitymonitor_7.1/config/dellpowerstore/publishingpools.webp)

**Step 3 –** Specify the name of the publisher.

**Step 4 –** Select the pool and click **Next**.

![configeventpublisher](/img/versioned_docs/activitymonitor_7.1/config/dellpowerstore/configeventpublisher.webp)

**Step 5 –** Specify Pre-Events Failure Policy as "Ignore - Consider pre-event acknowledged when
CEPA servers are offline".

**Step 6 –** Specify Post-Events Failure Policy as "Accumulate - Continue and persist lost events in
an internal circular buffer".

**Step 7 –** Click **Create Events Publisher**.

The events publisher is created.

## Enable Event Publishing for the NAS Server

Follow the steps tTo enable or disable event publishing for the NAS Server.:

**Step 1 –** Select **Storage** > **NAS Servers**.

![NAS Servers](/img/versioned_docs/activitymonitor_7.1/config/dellpowerstore/nasserver.webp)

**Step 2 –** Go to **[NAS SERVER]** > **Security & Events** > **Events Publishing**.

**Step 3 –** Enable and select the publisher.

![nasserver1](/img/versioned_docs/activitymonitor_7.1/config/dellpowerstore/nasserver1.webp)

**Step 4 –** You can enable the event publishing for all file systems on the NAS by checking the box
and selecting protocols.

Dell PowerStore is enabled for auditing.

## Enable or Disable Event Publishing for File System

Follow the steps toYou can enable or disable the feature for each file system individually. using
the following:

**Step 1 –** Select **Storage** > **File Systems** > **[FILE SYSTEM]** > **Security & Events** >
**Events Publishing**.

![Event Publising Option for File System](/img/versioned_docs/activitymonitor_7.1/config/dellpowerstore/fseventpublishing.webp)

**Step 2 –** Enable and select protocols needed.

Dell PowerStore is enabled for auditing.
