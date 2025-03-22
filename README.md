### Report on User and Group Management on Azure VM

The steps I took to manage users and groups on an Azure Virtual Machine. Below is a detailed account of the process:

1. **Connecting to the Azure VM**:
   First, I opened PowerShell and connected to the Azure VM using SSH. I made sure I had my key file ready and established the connection with the following command:
   ```sh
   ssh -i C:\Users\USER\.ssh\LandingPageVM_key.pem azureuser@20.197.228.244
   ```

2. **Creating New Groups**:
   After successfully logging in, I created new groups using the `groupadd` command. This was done to organize users based on their roles or departments.
   ```sh
   sudo groupadd hr
   sudo groupadd sales
   sudo groupadd strategy
   sudo groupadd executives
   sudo groupadd it_interns
   sudo groupadd finance
   ```

3. **Creating New Users and Assigning Them to Groups**:
   Next, I created new users and assigned them to the appropriate groups. I used the `useradd` command with flags to specify the user's shell and group.
   ```sh
   sudo useradd -m -s /bin/bash -G hr andrew
   sudo useradd -m -s /bin/bash -G legal julius
   sudo useradd -m -s /bin/bash -G hr chizi
   sudo useradd -m -s /bin/bash -G sales jeniffer
   sudo useradd -m -s /bin/bash -G strategy adeola
   sudo useradd -m -s /bin/bash -G executives bach
   sudo useradd -m -s /bin/bash -G it_interns gozie
   sudo useradd -m -s /bin/bash -G finance ogochukwu
   ```

4. **Setting Passwords for the New Users**:
   After creating the users, I set passwords for them using the `passwd` command. I noted that when typing the password, it would not be visible on the screen for security reasons.
   ```sh
   sudo passwd andrew
   sudo passwd julius
   sudo passwd chizi
   sudo passwd jeniffer
   sudo passwd adeola
   sudo passwd bach
   sudo passwd gozie
   sudo passwd ogochukwu
   ```

   For each `passwd` command, I was prompted to enter the new password and then retype it for confirmation.

5. **Verifying the Users and Groups**:
   To ensure that the users and groups had been created successfully, I used the following commands:
   - To list all users:
     ```sh
     cat /etc/passwd
     ```
   - To list all groups:
     ```sh
     cat /etc/group
     ```
   - To check specific user groups:
     ```sh
     groups andrew
     groups julius
     groups chizi
     groups jeniffer
     groups adeola
     groups bach
     groups gozie
     groups ogochukwu
     ```

### Summary
By following these steps, I successfully created groups and users on the Azure VM, assigned the users to their respective groups, and set passwords for them. This organization helps in managing permissions and access control based on the roles and departments of the users.

image of output is in outcome folders in this repo
