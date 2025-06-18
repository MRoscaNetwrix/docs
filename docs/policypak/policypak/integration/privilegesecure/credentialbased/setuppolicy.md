# Setting up the Endpoint Policy Manager Policy

After **Selecting Credential Based Policy**, fill in **Domain** and **User Name**.

![setting_up_the_policypak_policy](/img/product_docs/policypak/policypak/integration/privilegesecure/credentialbased/setting_up_the_policypak_policy.webp)

- Domain – Enter the name of the domain of the Netwrix Privilege Secure managed user to perform the
  activity.
- User name – Enter the unqualified name of the Netwrix Privilege Secure managed user to perform the
  activity.
- Activity name – Nothing to enter when Credential Release / always grayed out.

At the end of the policy you have some settings for **Action** and **Options**.

![setting_up_the_policypak_policy_1](/img/product_docs/policypak/policypak/integration/privilegesecure/credentialbased/setting_up_the_policypak_policy_1.webp)

In **Action**, you can select **Run with elevated privileges** or simply Allow and log if you just
want it brokered.

In **Options**, you can have the application launch be exclusively called with a right click **Run
with Netwrix Privilege Secure** context menu, or always call Netwrix Privilege Secure with **Apply
on demand** unchecked. Additionally, you can enable or disable video recording when this policy is
issued via **Enable video recording (Netwrix Privilege Secure)**.

Back on the Netwrix Privilege Secure server, you need to make sure there is a matching **Credential
Based** policy.

![setting_up_the_policypak_policy_2](/img/product_docs/policypak/policypak/integration/privilegesecure/credentialbased/setting_up_the_policypak_policy_2.webp)
