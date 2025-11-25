# KEST2 Assignment 6 – Security

---

## 13.2.3.7 Lab – BitLocker and BitLocker To Go

**1. Why is it important to save the BitLocker recovery key?**  
The recovery key is required to access the computer if the password is forgotten or if the system asks for it (e.g., after hardware changes).

**2. What is the role of the TPM (Trusted Platform Module) with BitLocker?**  
The TPM can store the encryption key and ensures the drive only works on a specific computer (binds the drive’s use to the hardware).

---

## 13.3.2.5 Lab – Configure Windows Local Security Policy

### Step 3 – Password Policy settings
- Maximum password age: **90 days**  
- Minimum password age: **1 day**  
- Minimum password length: **8 characters**  
- Password must meet complexity requirements: **Enabled**

### Step 4 – Account Lockout Policy
**1. How many login attempts are allowed before the user is locked out?**  
5 attempts.  
**2. How long must you wait before trying again?**  
5 minutes.

### Step 6 – Other Local Policies
**1. Anything recommended to change? Why?**  
Restrict "Domains trusted to authenticate logon attempts" and ensure only Administrators (or the appropriate admin team) have access.

**2. Settings:**
Policy | Security Setting
------ | ---------------
Devices: Allow undock without having to log on | Disabled
Interactive logon: Message title for users attempting to log on | Caution
Interactive logon: Message text for users attempting to log on | Your activity is monitored. This computer is for business use only.
Interactive logon: Prompt user to change password before expiration | 7 days

---

## 13.3.3.6 Lab – Configure Users and Groups in Windows

### Part 1 – Create New Users

#### Step 1 – View Local Users and Groups
**1. Which user accounts are visible?**  
Administrator, DefaultAccount, Guest, testUser, testUser2, tryggvi þor, user1, verkuser, WDAGUtility.

**2. Name five groups from Groups:**  
Administrators, Users, Guests, Event Log Readers, Power Users.

**3. Which group is your primary user in?**  
Administrators.

#### Step 2 – Create new users
**4. What must Student01 do at first logon?**  
Change the password.

**5. Which group is User01 in?**  
Users.

**6. Can members of the Users group make system changes? What are they allowed to do?**  
No. They can run applications and access most general files but cannot make broad system changes.

**7. Who are members of the group (Users / specified groups)?**  
Staff01, Staff02, Student01, Student02, test User, test User2, user1, verkuser.

#### Step 3 – Validate permissions
**8. Were you able to create a new user as a member of the Users group? Explain.**  
No, the Users group does not have permissions to create new users.

**9. Could you visit www.cisco.com?**  
Yes, members of the Users group can use the internet.

### Part 2 – Create New Groups
**10. With ITEStaff selected, what can members do in the folder?**  
Read & Execute, List Folder Contents, Read.

**11. Which additional permission would you choose?**  
Full Control.

### Part 3 – Modify User and Group Permissions
**12. Were you able to create the folder C:\Students\Student02 and a text file?**  
Yes. Members of ITEStudent have full access there.

**13. Were you able to create the folder C:\Staff\Student02 and a text file?**  
Partially. Student01 (ITEStudent) does not have access to the Staff folder but has full access in Students.

**14. Were you able to access contents in the Student01 and Student02 folders?**  
Only Student02 can access their own folder; no access to the Student01 folder.

**15. Could you access Staff, Student\Student01, and Student\Student02 as Staff01?**  
Yes. ITEStaff members have access to C:\Staff and C:\Student's folders.

#### Step 2 – Disable a user account
**16. Were you able to log in as Staff02?**  
No, the account is disabled.

### Reflection
**17. How do you give all ITEStaff administrator privileges on the machine?**  
Add the ITEStaff group to the built-in Administrators group: Computer Management > Local Users and Groups > Groups > Administrators > Add > ITEStaff.

**18. How do you deny access to a file to everyone except the owner?**  
Give the owner Full Control; set an explicit Deny on all permissions for other groups and users.

---

## 13.3.4.6 Lab – Configure Windows Firewall

mynd
---

## 13.4.1.10 Packet Tracer - Configure Wireless Security
