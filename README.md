# Active-Directory-
This scenario was assigned to me to add specific groups to a network through active directory 
# Active-Directory-
This scenario was assigned to me to add specific groups to a network through active directory 
### Task 1: Create a GPO: Disable Local Link Multicast Name Resolution (LLMNR)
#### Instructions

Create a Group Policy Object that prevents your domain-joined Windows machine from using LLMNR:

1. On the top-right of the Server Manager screen, open the Group Policy Management tool to create a new GPO.

2. Right-click **Group Policy Objects** and select **New**.

3. Name the Group Policy Object `No LLMNR`.

4. Right-click the new **No LLMNR** GPO listing and select **Edit** to open the Group Policy Management Editor and find policies.

5. In the Group Policy Management Editor, the policy you are looking for is at the following path: `Computer Configuration\Policies\Administrative Templates\Network\DNS Client`.

    - Find the policy called `Turn Off Multicast Name Resolution`.

    - Enable this policy.

6. Exit the Group Policy Management Editor and link the GPO to the `GC Computers` organizational unit you previously created.

---

### Task 2: Create a GPO: Account Lockout

#### Instructions

You'll be working within in your nested Windows Server machine again to create another Group Policy Object.

Create what you believe to be a reasonable account lockout Group Policy for the Windows 10 machine. 

1. Name the Group Policy Object `Account Lockout`.

2. You can use Microsoft's 10/15/15 recommendation if you'd like.

3. When editing policies for this new GPO, keep in mind that you're looking for _computer configuration_ policies to apply to your `GC Computers` OU. Also, these policies involve Windows _security settings_ and _accounts_.

4. Don't forget to link the GPO to your `GC Computers` organizational unit.

---

### Task 3: Create a GPO: Enabling Verbose PowerShell Logging and Transcription

#### Instructions 

For this task, you'll be working in your **Windows Server** machine.

Create a Group Policy Object to enable PowerShell logging and transcription. This GPO will combine multiple policies into one, although they are all under the same policy collection.

1. Name the Group Policy Object `PowerShell Logging`. 

   - Find the proper Windows Powershell policy in Group Policy Management Editor. 

2. Enable the `Turn on Module Logging` and do the following:

   - Click **Show** next to **Module Names**.

    - Since we want to log _all_ PowerShell modules, enter an asterisk `*` (wildcard) for the Module Name, then click **OK**.

3. Enable the `Turn on PowerShell Script Block Logging` policy.
