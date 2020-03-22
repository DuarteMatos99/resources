**Author:** Duarte Matos

###### tags: `G Suite`

# Introduction G Suite

![](https://i.imgur.com/iGRfPA9.png)

## What's G Suite?
G Suite is a package of cloud-based services that can provide your company or school with a whole new way to work together online -- not just using email and chat, but over video conferences, social media, real-time document collaborations, and more.

![](https://i.imgur.com/ZtForkg.png)

## Admin Console
Easily add users, manage devices, and configure security and settings so your data stays safe. 

This app:
- Is your first place to manage G suite domain
- We can use GAM(Command line tool), the mobile app, the oficial site and APIs
- Role based admin roles (distribute the roles based on a specific function or need on your department)
- Most settings can be done there, but not all... (GAM and APIs we can code specific areas)

# Account Setup
## Setup a new G Suite account
After setup a new G Suite account we need:
1. Activate Gmail(automatically or manual)
2. Activate Cloud Identity Free on **Billing**
    - Manage more users and applications to secure your data in the cloud

## Review your Domain Name System (DNS) 
### Introduction
Before you can use any G Suite service Google must verify that you own the domain you intend to associate with your G Suite account.

There are a number of ways you can verify ownership but the most common method is by adding a TXT record to your domain’s DNS records. This record is provided by Google. When you signed up for the G Suite trial earlier, Google added the verification record for you so you don't need to do any more for the purposes of this training. However, if you wanted to use G Suite with an existing domain, you will need to add this record yourself.

Even though you do not need to verify your training domain it is very useful to understand the the different types of DNS records that you need to work effectively with G Suite. In this exercise you will log into your domain registrar and review the records that Google uses.

### Directions
==Please note:== The DNS records discussed here are added by Google only if you purchased your domain during the sign-up flow. Advanced DNS settings credentials are also only visible for domains purchased during sign up.

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Domains** icon.
3. Click **Add/remove** domains or the **Manage Domains** icon and then expand the **Advanced DNS settings** section (center of the page). This will reveal your domain registrar username and password.
4. Click the **Sign into DNS console** link and login to your domain registrar. You should now be able to review your domain’s DNS records.

Look for your 'google-site-verification' record. It will look something like this:

![](https://i.imgur.com/RXxsH6e.png)

In addition to the site verification record Google will have added some additional records:

- A **Sender Policy Framework (SPF)** ==TXT record== (this allows receiving mail servers to verify that the sending servers are authorized to send mail on your domain’s behalf)
- A number of **CNAME (Alias)** ==records can be used to alias one name to another== (which you can use to provide more user friendly URLs to core Google services such as Gmail and Calendar).
- **Mail Exchanger (MX)** records (ensures mail is routed to Google’s servers)

Examples of these are below. Check that they exist in your DNS records

![](https://i.imgur.com/8SNmrGU.png)

![](https://i.imgur.com/W9pRa8A.png)

==Notes:==
The column names may vary from those above depending upon the registrar you chose when you signed up for the G Suite trial.
There are typically 5 MX records. We have just shown the first three here to keep things simple.

5. Sign out of your domain registrar.

### Existing domain considerations

Where you want to use an existing domain with a G Suite account you will need to verify the domain using one of the options allowed by Google.

In addition to verifying your domain, if you are using Gmail you will need to update your Mail Exchanger (MX) records to direct mail to the Google servers.

It is recommended that you add an SPF record for your domain. If you do not set up SPF, some messages may bounce or be marked as spam. 

## Personalize the Admin Console
### Introduction
The admin console home page shows controls or icons that launch various administrator settings, and has links to tools and common administrative tasks.

The first time you first sign in to the admin console, only the default most commonly used controls are visible. You can add new controls and hide any that you don’t need. You can also move the controls on the screen to suit your desired ordering.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com. The first time you first sign in to the admin console, only a few controls or icons are visible in the dashboard.

3. Click **MORE CONTROLS** at the bottom of the page to reveal hidden controls.

4. Drag and drop the following icons up into the main area of the page:
    - Buildings and Resources
    - Reports
    - Rules
    - Security

==Tip:== If you move your mouse cursor over a hidden control a small gray + sign will be revealed on the top-right of the control’s icon. Clicking the + sign adds the control to main page so you don’t need to drag and drop.

Your admin console should look similar to this. Don't worry if you forgot an icon, you can always move it later.

![](https://i.imgur.com/ZkdVPYp.png)

4. Click the three horizontal lines on the top left of the screen to reveal the side menu. This menu makes it easier to see, find, and directly navigate to the information and settings in your admin console:

    - Easily scan a shorter, multi-layered menu that helps you find things quickly.
    - Quickly find what you’re looking for by hovering over and clicking through the menu to drill down directly to the pages you want to see.
    - The streamlined menu removes clutter for delegated admins so they will only see the menu items they have access to with their level of administrative privileges.

![](https://i.imgur.com/f8CyUvJ.png)

==Tip:== Click Google Admin at the top left of the screen to return the home page at any time, or click Home from the side menu.

## Review your Company Profile
### Introduction 
The Company profile is where you define company-wide settings for properties such as language, time zone, and company name. You also use this profile to manage policies such as when users can see newly released features in G Suite services.

## Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Company profile** icon.
3. Click the **Profile** section.

This is where you can configure company-wide settings. Explore the various profile settings.
- The 'Organization name' will be taken from the information that you provided when you signed up for G Suite. This may be your domain name or the business name you entered at that time. This name that will appear to your users in many G Suite services.
- The email addresses found in the 'Contact information' section also match the information that was provided during the sign up process.
- You can use the 'Support message' section to enter a message users will see when they sign into the User Hub. This is a useful place to add details advising your users how to contact support.
- Verify the 'Language' and 'Time zone'. These represent the default settings for new accounts.
- The 'New User Features' setting is where you control how fast new features are released to your users for existing services. Scheduled Release is the default and recommended setting. Choose this track to delay releasing new features to users (typically 1-2 weeks following rapid release) which will give you more time to train your support staff and prepare users for the coming changes. 
- The 'New products' setting allows you to control whether new G Suite services become available to your users as they are released or not.

4. if you have made any changes, click **SAVE**.
5. Click the **Personalization** section. This is where you can upload your company logo and brand the G Suite services for your users. Optionally, create an image file and upload it to your company profile. The recommended size for a logo image is 320 x 132 pixels.

### Other Settings
**Communication preferences:** Set which communications you wish to receive from Google. By default all options are disabled.

**Supplemental Data Storage:** Specify an additional country in which you want your user’s data stored. This is a company-wide setting.

**Legal and Compliance:** Find links to legal and compliance information and contact details.

**Data regions:** Set policies which control where your user’s data is stored in Google’s data centers.

**Custom URLs:** Define user friendly URLs to your core G Suite services.

**Account management:** Used to delete your G Suite account

## Account setup Quiz
1. What type of DNS record allows receiving mail servers to verify that the sending servers are authorized to send mail on your domain’s behalf?
==R: SPF==

2. What must you do before you can start to use G Suite services?
==R: verify that you own the domain you intend to associate with your G Suite account==

3. Typically how long after a new features are released to the Rapid release track will they be released on the Scheduled release track?
==R: 1-2 weeks==

# Adding Users
## Introduction
Each person in your organization needs a user account to use Google services and each account requires a G Suite license. There are a number of ways to add (or provision) your users. You can add them one at a time, in bulk through a Comma Separated Values (CSV) file upload, via the Admin SDK Directory API, or using a third party tool such as Google Cloud Directory Sync (GCDS).

## Add Users Individually
### Introduction
In this exercise, you'll manually add an individual user: Alex Bell, the IT Manager.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Users** icon.
3. Click **Add new user**.
4. In the dialog box that appears, create your company's IT Manager user account as follows:
- First name: Alex
- Last name: Bell
- Primary email: alex.bell@yourdomain

==Tip:== If your account has multiple domains associated with it, you will see a domain drop-down list so you can choose the correct domain for each new user. The domain is the part of the user's email address that appears after the @ symbol.

- Each user is assigned to an organizational unit. At this stage of the course we have just one single top level organization so Alex will by default be placed into that organization. We will discuss organizational structure later in this course.
- Leave the secondary email and phone number fields empty.
- You can assign a temporary, randomly generated password or manually enter a temporary password. Note: Passwords must be at least 8 characters long and cannot exceed 100 characters. Either way, it’s best practice to ensure that the new user changes this when signing in for the first time so ensure that 'Ask for a password change at next sign in' is enabled. For this exercise, allow G Suite to generate the temporary password.

5. Click **ADD NEW USER** to create Alex's account.

Congratulations! You've added your first user in your new domain!

Notice the 'Show Password' link in the dialog box. This allows you to see the temporary password generated. You can also copy the password to your clipboard using the 'Click to copy password' link. Alternatively, click MORE ACTIONS from where you can either email or print the login details for your new user.

6. Click **DONE**.

## Add Several Users at Once
### Introduction
You've learned how to add users manually; however, when adding many users at once, this method is quite time consuming. Let's see how to bulk upload multiple users at once.

### Scenario
You receive this mail from the IT Manager, Alex:
Hey G Suite Admin,

Thanks for creating my G Suite account. Now our next task is to get the rest of our user accounts created. Below is a list of people.

![](https://i.imgur.com/sAM4ZyB.png)

Can you create these user accounts?

Thanks,

Alex Bell, IT Manager

### Directions
==Download the template file==

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Users** icon.
3. Click **Bulk upload users** then click the **CSV template** link. This will download a blank file with all the required columns to your local machine. Leave this dialog box open to upload the file after editing. 

==Add user information==

4. Open the CSV file in a spreadsheet application or a text editor if you prefer.

5. Edit the file and add the user data. Copy the user information into the CSV file from the table Alex provided.

The file contains a column for each attribute that appears on the user profile in the admin console and in Gmail contacts.

The following columns are mandatory:

- First Name
- Last Name
- Email Address
- Password (enter hellohello1)
- Org Unit Path (For this exercise, enter the forward slash symbol / into this column. This represents the root organization)

Don't forget to update the domain in the email addresses. The other columns aren't mandatory, so you can enter values or leave them blank. However, Alex has also provided a column for **Employee Title** so you should complete that column also.

==Upload the file==

6. Once the editing is complete, save a copy of the file as a CSV file back to your local machine. To do this in Google Sheets while you still have the file open in Sheets, click **File > Download As > Comma Separated Values (.csv, current sheet)**.

7. Return to the 'Bulk upload users' dialog box, click **ATTACH CSV** and browse to the edited spreadsheet you just saved locally, then click **UPLOAD** to initiate the creation of the user accounts.
    - If your file has formatting errors, a warning prompts that you may need to re-edit the file.
    - If successful, the progress of the upload will be reported in the **YOUR TASKS** list at the top of the page. You'll also receive an email report later.

8. The new users may take a couple of minutes to appear in the user list. If you don’t see them right away, try refreshing the screen. Review the list of users and explore the user settings.

Congratulations! You created multiple users at once!

### Notes
It can take up to 24 hours for new user accounts to appear in the searchable domain directory.
If you're uploading more than 500 user accounts, you can optimize the experience by splitting your uploads into smaller batches.

## Sync Users to G Suite with GCDS
### Introduction
As we have seen G Suite accounts can be created manually or in bulk. Either method works well but these methods are more applicable to smaller customers where less frequent user maintenance is needed.

Larger organizations often require a more automated approach to account management. Such customers may choose to deploy **Google Cloud Directory Sync (GCDS)** which can provision G Suite accounts directly from Microsoft® Active Directory® or LDAP server. In addition to account creation GCDS ensures that users, groups, and shared contacts in G Suite are synchronized with updates that are made to the local directory.

==GCDS never modifies local directory information. Updates are only made to the Google Cloud Directory to reflect local changes.==

### Who should use GCDS
GCDS is particularly relevant to organizations that have a pre-established directory. Using GCDS removes the need to separately manage the Cloud Directory as it performs a one-way synchronization ensuring Google domain data matches the local directory at all times.

## Provision Users using the Admin SDK API
### Introduction
G Suite includes many Application Programming Interfaces (APIs) that allow customers and third party developers to integrate with G Suite services and data. One of these APIs is the **Admin SDK** *which can be used to automate administrative operations on users, groups, organizational units, and devices in your G Suite account*. Included in the Admin SDK is the **Directory API** *which includes methods to create and manage your user accounts.*

==GCDS actually uses the Directory API to provision and manage user accounts as part of the sync process.==

## Adding Users Quiz
1. Your company just acquired a 100-employee startup and you quickly need to add the new employees to your domain. Using the Admin console, which is the most efficient way to add new users all at once?
==R: Add all the new users at once from a .csv file.==

2. When adding users individually, how are passwords established?
==R: The admin can enter a password manually or allow the console to generate a temporary password for the new user.==

3. Which of the following are required when adding multiple users via a CSV file?
==R: First Name, Last Name, Email Address, Password(All of these)==

4. What is the minimal amount of characters required of G Suite passwords?
==R: 8 characters==

5. How does GCDS sync directory information?
==R: It updates G Suite with information from the local LDAP directory.==

# Adding Groups
## Introduction
The Google Groups service includes:

- Admin console groups: Groups used for communication, collaboration, and administration. Administrators create and manage these groups in the admin console.
- Groups for Business (managed by administrators and users): Groups used for communication and collaboration. When you turn on Groups for Business, you and your users can manage group features in Google Groups (groups.google.com).

Groups can be created from the admin console, from the Google Groups for Business service, or using the Admin SDK Directory API. GCDS can also be used to sync admin groups from any LDAP compliant directory to G Suite.

In this lesson you will also create two groups for your organization from the admin console. We will look at group settings later in this course.

## Create Admin Managed Groups
### Introduction
In this exercise you will create two groups from the admin console. Read through the scenario and directions below in order to practice creating admin managed groups.

### Scenario

You receive this mail from Sam, the CEO:

Hey G Suite Admin,

We would like to have a group email address where I (and only I) can send company wide announcements to everyone.

I would also like to setup a team group for the use of the executive and managers only.

Can you please create these groups for us? Thanks,

Regards, Sam Morse, CEO

### Directions

==Create the group for all employees==

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Groups** icon.
3. Click **Create group** and enter the following information:

Name: All employees
Description: Internal mailing list for everyone.
Group email: everyone@yourdomain

4. Click **NEXT**.

5. Set the 'Access type' to Announcement only. Anyone in the organization can view topics but only owners can post.

6. Click **CREATE GROUP**.

7. Click the **Add Members to All employees** link.

8. In the resulting page, click on the yellow circle with the + sign to add members and then click the **Advanced** link at the bottom of the 'Add member to All employees' dialog box.

9. Check the 'Add all current and future users of ```<your company>``` to this group with All Email setting' box and click **ADD TO GROUP**. New users will be automatically added to the group as they join your organization.

10. Refresh the screen, you should see the member list has one entry called 'All users in the organization'. Note: New users will be automatically added to the group as they join your organization.

11. Repeat Step 8 but this time enter Sam's email address. She will be added to the member list with the Member role.

12. Hover over Sam and click the down arrow in the Role column and click **Manager** to make her the group manager.

13. Click **SAVE**.

Sam can now email everyone in the organization by emailing everyone@yourdomain.

==Create the management group==

14. Return to the Groups page and create a new group as follows:
    - Name: Management
    - Description: Executive group
    - Group email: management@yourdomain

15. Set the 'Access type' to Restricted (Only members can post and view topics), create the group and add the following members:
    - Samantha Morse (CEO)
    - Alex Bell (IT Manager)
    - Lars Ericsson (HR Manager)

16. Change Sam's role to be a group manager so she can add new members as needed.

The management team now have a private group in which to collaborate.

==Verify group settings==

17. Sign out and sign back in to G Suite at mail.google.com as samantha.morse@yourdomain.

18. Send a message to everyone@yourdomain and another message to management@yourdomain.

19. Open the Groups for Business service at groups.google.com.

20. Click **My groups**. You should see the both groups listed. Open each group in turn and verify that your messages were delivered.

21. Sign out and sign back in to G Suite at mail.google.com as mark.jones@yourdomain. You should see the message sent by Sam to everyone in your inbox.

22. Send a message to everyone@yourdomain and another message to management@yourdomain.

23. Refresh your inbox (you may need to do this a few times). You do not have permissions to post to either group so should receive a delivery failure report for each of the two messages.

24. Sign out and sign back in to G Suite at mail.google.com as lars.ericsson@yourdomain. Lars is a member of the Management group so you should see both messages sent by Sam earlier in your inbox.

25. Send a message to everyone@yourdomain and another message to management@yourdomain.

26. Refresh your inbox (you may need to do this a few times). You should receive a delivery failure report for the message sent to everyone@yourdomain only.

27. Open the Groups for Business service at groups.google.com.

28. **Click My groups**. You should see the Management group listed. Open the group and verify that your message was delivered.

### Notes
1. Administrators, even if not members of a group have all privileges in the admin console.
2. Using the Groups for Business service, your users can also create their own groups. They can create simple email lists, web forums, Q&A groups and collaborative inboxes. As the administrator you can see and manage any of these user created groups from the admin console.

## Adding Groups Quiz
1. What methods can be used to create a Google Group?
==R: Admin console, google groups, GCDS(All of the above)==

2. You have created an Announcement group and you want to ensure that all users in your organization receive emails sent to the group. How would you do this?
==R: Check the 'Add all current and future users of ```<your company>``` to this group' setting when adding members for the first time.==

3. What type of groups can be created from the Groups for Business service?
==R: Q&A groups, Web forums and Collaborative inboxes.==

4. What type of groups can be created from the Groups for Business service?
==R: Create a restricted group with all users in the domain and assign the role of the group owner or manager to the CEO and the executive staff.==

# Adding Buildings, Features and Calendar Resources
## Introduction
In addition to scheduling meetings in Google Calendar, G Suite users in your organization can manage shared resources. The most common example of a resource is a meeting room. Other examples might include projectors, company fleet cars, or any other resource people might schedule a time to use.

It's recommended that you define your resources using a structured format that includes information about the resource location, capacity, or equipment. Calendar uses this data to give more room and resource details, helping your users choose the best resource for their needs. Structured resource naming will give your users the best experience in Google Calendar so it is worth making an effort when adding resources to your organization.

Setting up your resources involves three steps. First you will add your building information, then you will add any features, e.g: video, audio, and finally you will add the resources themselves.

Buildings, features and resources are created from the admin console. They can also be uploaded in bulk via a CSV file or created using one of the resources methods available in the Admin SDK Directory API.

In the following exercise you will add two calendar resources after first defining your building and adding some common features that might be found in each resource.

==Buildings== : Start by listing all the buildings in your company. Google Calendar uses buildings as the foundation for all your resources. You can’t create resources and features without listing the building first. Note: Building addresses are not used for map navigation.

==Features== : If you want people to know what equipment or other features come with a room or other resource, add them using the Admin console. For example, you might want to let people know which rooms have a Jamboard, or which company cars have a navigation system.

==Resources== : Next, add anything people can reserve: conference rooms, company cars, mother's rooms, or whatever your company provides for workers. If you created features in step 2, you can associate them with the resources as you add them. 

## Adding Calendar Resources
### Introduction
In this exercise you will create two structured calendar resources for your main building. You will also define some features that can be applied to each resource. Read through the scenario and directions below in order to practice creating admin managed groups.

### Scenario

You receive this mail from the IT Manager, Alex:

Hey G Suite Admin,

We would like to allow our users to book a couple of our meeting rooms directly from Google Calendar. Can you please add the main boardroom, and the top floor conference room information to our calendar system.

Thanks,

Alex Bell, IT Manager

### Directions

In the following instructions, let's assume that you have gathered details about the facilities (features) available in each of two rooms. The first step is to add your building details.

==Add building==

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Buildings and resources** icon.
3. Click **EDIT RESOURCES**.
4. Click **ADD BUILDING**.
5. Click on the yellow circle with the + sign to add a new building. Complete the dialog as follows:
    - Name: Head Office
    - Description: Main work location
    - Floors: 1,2,3,4
    - Address: Enter your address
6. Click **ADD BUILDING**.

==Note:== The Building ID is used to associate a resource with a particular building which is why you must define your buildings first.

==Add features==

7. In the navigation at the top of the page, switch the view from Buildings to Resources.
8. Click the 'Manage resource features' icon (three horizontal lines with a pencil icon over the bottom line) which is located in the top right corner of the Resources list.
9. Click **ADD FEATURE** and enter the following details:
    - Feature name: Refreshments
    - Feature type: Other
10. Click **SAVE**.
11. Click **ADD FEATURE** and enter the following details:
    - Feature name: Google Meet Hardware
    - Feature type: Video conferencing
12. Click **CLOSE**.

Our features are added so it is time to add our resources.

==Add resources==

13. Click on the yellow circle with the + sign to add a new resource. Complete the dialog as follows:

    - Category: Meeting space (this should be the default)
    - Type: Meeting room
    - Building: Head Office (this should be the only entry available as you have only added one building)
    - Floor: 4
    - Floor section: This indicates where on the floor the room is located. It's optional but enter East.
    - Resource name: Conference room
    - Capacity: 10
    - Features: Select Google Meet Hardware
    - User visible description: Extension 326 (Free-form description of the room that is visible to users in the room details)

14. Click **ADD RESOURCE**.

15. Click on the yellow circle with the + sign. Now add your second resource as follows:

    - Category: Meeting space (this should be the default)
    - Type: Meeting room
    - Building: Head Office (this should be the only entry available as you have only added one building)
    - Floor: 2
    - Floor section: This indicates where on the floor the room is located. It's optional but enter West.
    - Resource name: Boardroom
    - Capacity: 20
    - Features: Select Google Meet Hardware and Refreshments
    - User visible description: Extension 316 (Free-form description of the room that is visible to users in the room details)
16. Click **ADD RESOURCE**.

Congratulations, you have just added two structured calendar resources to your G Suite account.

==Explore the settings==

17. From the list of resources, click on the Conference room row to open the resource details. On the left hand side you will see an email address and an auto-generated resource name in the following format:

    - Resource email: yourdomain_1993ce917vkushojkrbuv2ckpu2t66gb68o34dpk64q3icph70@resource.calendar.google.com

    - Auto-generated resource name: Head Office-4-East-Conference room (10) [Google Meet Hardware]
18. Open your Google Calendar and click the + button to the right 'Other calendars' and select **Browse resources**. You should now see the two resources listed. Check each of them to subscribe. The two resources should now appear in your list of calendars.

19. Create a test event and start typing Head office into the 'Guests' field. You should see the two resources listed in autocomplete for selection.

### Notes
Resources may not show immediately in Google Calendar.

If you are unable to see the resources in Google Calendar, try again later or try clicking the + button to the right of 'Other calendars', then select **Subscribe to calendar**. Then paste the resource email address into the 'Add calendar' field.

Resource calendar settings such as sharing settings are managed from Google Calendar.

### Calendar Resources Quiz
1. Which of the following statements are true? (Choose 2)
==R: Resources are normally associated with a building so it is recommended that buildings are definied first and you choose the building when adding the resource.==
==R: Features (such as video, audio equipment) are associated with a Resource.==

2. Once you have created your resources, how do you manage the resource calendar settings?
==R: From Google Calendar==

3. What can be defined when creating a Resource? (Choose 2)
==R: Name
R: Capacity==

# Managing Users
## Introduction
Earlier you learned how to add new user's to your G Suite organization.

Ongoing user accounts management is a core function of the G Suite administrator, and something that you will do on a daily basis. In this lesson you will complete a number of exercises where you will learn how to undertake some of the more common user management tasks in G Suite.

## Add an Email Alias for a User
### Introduction
Now that you've added a larger batch of users, some of your users have already signed in and started to use G Suite. In this exercise you will be given a scenario where you are asked to create an email alias for a user. An email alias allows a user to receive email sent to multiple addresses in their Gmail inbox.

An **email alias** is a way to create an additional name for your email account. This allows you to create alternative email addresses without having to create another email box. Keep in mind you **can not send from an alias**.

==Example:==

If your email address is user@domain.com and you create an alias "user2@domain.com" that means that if someone emails user2@domain.com, you will be able to login to your user@domain.com email address and view that message.

### Scenario
You receive this email from the CEO:

Hello G Suite Admin,

Thanks for creating my G Suite account. However I have to ask for a minor change. My email is samantha.morse@yourdomain but really most people know me as just “sam”. Is there any way I can have this as my email also?

Regards,

Sam Morse, CEO

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Users** icon.
3. Locate Samantha Morse in the user list, click her name, and click the **User information** card.
4. Click the **Email aliases** section.
5. In the **Alias** text field, enter sam and click **SAVE**.
6. Now notify Sam about her new email alias and remind her about its limitations:

Dear Sam,

I have created a new email alias for you. In addition to your primary email address, samantha.morse@yourdomain, you can now also receive mail sent to sam@yourdomain.

However, please be aware that you'll still need to use your primary email address: samantha.morse@yourdomain to sign in to G Suite.

Note that it may take up to 24 hours for the email alias to become available.

Regards, Your G Suite Admin

### Notes
If you add a domain alias every email address in the primary domain automatically has an email alias address in the alias domain. We will discuss domains in more detail later.

## Reset a User's Password
### Introduction
As the administrator you're likely to come across a situation where a user needs their password to be reset.

- A user may simply forget their password
- A user's account is compromised (security concerns)

G Suite includes a feature that allows users to recover their own password but this is disabled by default, and each user must add a recovery phone or email address to their account for this feature to work.

Where the user does not know their password, and recovery information has not been added (or if self-service recovery is not enabled), the administrator must reset the password.

### Scenario
Tim Lee has just come back from vacation, he calls to ask you to reset his password, because he's forgotten it and is now locked out of his account.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click on the **Users** icon.

3. Access the reset password function by one of two ways:

- Hover over Tim Lee in the user list and click **Reset password** on the right.
- Click on Tim Lee in the user list to open his profile and then click **RESET PASSWORD** on the left.

4. In the 'Reset password' dialog box:

- Fill in a temporary password or click **Auto-generate password** to let Google create one for you.
- Check the 'Ask for a password change at the next sign-in'.
- Click **RESET**.
- Click the **Click to copy password** link to copy the password to your clipboard.
- Click **DONE**.

5. Provide Tim with his new password. When he next signs in he will be asked to change his password.

### Notes
Users can change/reset their existing password if they know their existing password and can successfully sign in.

If the administrator has enabled non-admin password recovery users can reset their password without administrator assistance. Note that this feature is not available for customers using Single Sign-on (SSO).

Admins should check the Help Center for considerations regarding user off-boarding, and hijacked accounts before enabling this feature.

## Rename a User
### Introduction
As an administrator for your organization's G Suite service, you change a user’s email address in the admin console. You can also change the display name that shows up in emails they send, calendar invites, and so on. Users can also change their own display name but they can’t change their address.

### Scenario
You receive this mail from the Tim Lee:

Hello G Suite Admin,

Thanks for resetting my password. I have another issue with my account, maybe you can help. I don't ever use the name Tim. At work I go by my full name Timothy but all my friends and coworkers call me Timmy. Can you fix my account so I login and mail with my preferred names?

Thanks,

Timothy Lee, Finance

You decide that the best way to implement this is rename the user to timothy@yourdomain to allow him to sign in and use his mail with this new username. Then add an alias of timmy@yourdomain to the account.

### Directions

1. Ask Tim Lee to sign out of his G Suite account.

2. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

3. Click the **Users** icon.

4. In the user list, hover over Tim Lee and click **Rename user** on the right.

5. In the 'Rename user' dialog box, read the warning message and enter the following:

    - First name: Timothy
    - Last name: Lee
    - Primary email: timothy.lee. This is the username he'll use to sign in to G Suite.

The First and Last name settings represent the Display Name.

6. Click **RENAME** and then click **CONTINUE** to confirm the change.

Now that you have renamed the user to allow him to use his full name (Timothy) to sign in and send mails, let's look at his other request to use the name Timmy to send mail.

7. If you are not already in Timothy's user profile select Timothy Lee from the users list.

8. Expand the **User information** card and click on the **Email aliases** section. Notice here that Tim’s original email address tim.lee@yourdomain has been added as an alias. This is to ensure that he can still receive mail sent to his old primary address.

9. Add a new alias Timmy and click **SAVE**.

Now you can see the difference between just adding an alias for a user and renaming a user.

### Notes
It can take up to 10 minutes for a new primary email address (rename) to be reflected throughout the system, 24 hours for domain and personal contact changes to take effect, and up to 3 days before the user can use chat.

It can take up to 24 hours for the alias to become available.

## Suspend a User
### Introduction
As a G Suite administrator, you can temporarily block a user's access to G Suite services by suspending the user's account. This disables the account without deleting the user or any data in their account. Any content that they own and have shared with others remains accessible to collaborators.

A suspended user can't sign in to the account, and new emails and calendar invitations are blocked. As the account is not deleted a license fee still applies.

### Scenario
You receive this email from Lars Ericsson, the HR Manager:

Hey G Suite Admin,

I had a contractor working with me last week for a project, his name is Jon Baird. He has an account to sign in to our system but for the next few weeks he'll be working somewhere else. Is there a way to prevent him from signing in without losing all the work he's done already? He'll be back to work with us soon.

Regards, Lars Ericsson

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Users** icon.
3. Locate Jon Baird in the list and hover over his name, then click **More > Suspend user**.
4. Click **SUSPEND**. The Status column for Jon will change from Active to Suspended.

==Tip:== To view only suspended users, click Add a filter > User status, select Suspended and APPLY the filter. Your filter will also show at the top of the screen. Clear the filter by clicking the cross to the right of the filter value.

### Scenario (continued)
A few weeks later, you receive another email from Lars Ericsson, the HR Manager:

Hey G Suite Admin,

I have a contractor, Jon Baird, who will be working with us again next week. He had an account before but is locked out at my request. Can you please re-enable him?

Regards, Lars Ericsson

As a G Suite administrator, you can restore a user you (or another administrator) suspended.

### Directions (continued)
1. In the user list, filter for suspended users. Locate Jon Baird in the list and hover over his name, then click **More > Reactivate**.
2. Click **REACTIVATE** to confirm. Jon will be removed from the suspended user list.
3. Clear the filter and confirm that Jon’s status has been changed back to Active.

Jon can now sign in and has full access to his account and data.

### Notes
Administrators manually suspending users is just one way that a G Suite account can be suspended or disabled. If the user is manually suspended by an administrator, it's possible for an administrator to restore their account immediately.

A user can also be automatically suspended from Gmail for exceeding Email sending limits. In this case, the user can still sign in to their G Suite account to access other services, such as Calendar and Drive. But when they try to access Gmail, an error prompts that Google detected unusual activity on the account. Most users will regain access automatically within 24 hours, but in some cases, an administrator can reset the limits for the user and allow them to immediately regain access.

You cannot restore an account that was suspended for abuse or for breaching Google’s Terms of Service.
You cannot restore a user with an abusive account status. Administrators can contact Google Support for more information.

## Delete a User
### Introduction
When a user leaves your organization you might want to delete their G Suite account. This deletes all of their data and they'll no longer be able to sign in to G Suite. It's important to understand the difference between account deletion and suspension,  so you should develop a process for users leaving the company, and create a policy that best suits your business needs.

Once you delete the account data is retained for a period of 20 days so this does give you the opportunity to restore an account should you need to within a limited time frame. In addition, it is also possible to transfer certain data (Docs, Calendar, Google+ pages) to a new owner at the point of account deletion.

Be aware that there are many other considerations that you should be aware of before deleting an account; there may be many other types of data that could be lost without following proper steps.

### Scenario
After some time working in the G Suite domain, you get another email from Lars Ericsson, the HR Manager:

Hey G Suite Admin,

That contractor I had working with me, Jon Baird, has finished up his project. Can you please delete his account from the system as he won't be working here anymore? Will you make sure that any files he still has belong to me now? Don't want to lose anything important.

Regards, Lars Ericsson

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Users** icon.
3. Locate Jon Baird in the list and hover over his name, then click **More > Delete user**.

You now have the option to transfer certain types of data from Jon’s account to a new owner. Lars has asked you to transfer ownership of all of Jon’s files to him.

4. In the dialog ensure 'Drive and Docs' is selected and check 'Include files that are not shared with anyone'. You can deselect 'Calendar and Google+ Pages'.
5. Search for Lars Ericsson to complete the 'Transfer to' field and click **DELETE**.

Jon’s account will now temporarily be suspended whilst the transfer takes place. The account will then be deleted.

6. Click **DONE**.
7. Check your inbox. You should receive a notification confirming that the deletion was successful.

## Restore a Recently Deleted User
### Introduction
The G Suite super administrator can restore a user account up to 20 days after deleting it. After this period, the admin console permanently deletes the user account and it can't be recovered, even by Google technical support.

In most cases, restoring a deleted user account also restores the user's associated data, including email and calendar events; however, Google doesn't guarantee full data recovery for a deleted user.

### Scenario
The next day you get a high priority email from Lars Ericsson, the HR Manager:

Hello G Suite Admin,

I'm afraid I was a little premature in getting you to delete our Jon Baird’s account. We've decided to hire him as a full-time employee.

Is there any way you can restore his user account?

Regards, Lars Ericsson

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Users** icon.
3. Click **Add a filter** and select **Recently deleted**.

==Tip:== If you have multiple organizational units , complete this action from the top level organization. Deleted users lose their organization details and are moved to the top level organization. We will discuss organizational structure later in this course.

4. Locate Jon Baird in the list and hover over his name, then click **Recover**.
5. Click **CONTINUE**.
6. Select your top level organization and click **RECOVER**.
7. Clear the **Recently deleted** filter to return the user list. It can take up to 2 hours to restore account but you should shortly see Jon appear in the list.
8. If a user was suspended at the time the account was deleted, such as when you transfer ownership of data, the user will remain suspended after the account is restored. To reactivate Jon, locate him in the user list and hover over his name, then click **More > Reactivate**. Then click **REACTIVATE** to confirm.

### Notes
You can restore only one user at a time.

It may take some time for the user to be visible again in the active user list.

When you restore deleted users after transferring the ownership of their files to other users, the restored users do not automatically acquire ownership of their old files. Instead, they can only edit the files they previously owned.

## User Licenses
### Introduction
Every user needs a license to use a Google service. For example, a user must have a license for G Suite before they can use Gmail, Google Drive, or any other G Suite service.

There are two types of license, a **site-based license** and a **user-based license**. When you sign up for a service that has a site-based license such as Android every user in your organization gets a license so you don't need to assign this type of license. User-based licenses, such as a G Suite license may need to be assigned depending upon your subscriptions and this can be done manually or automatically.

### Assigning licenses
If you purchased just one subscription, e.g: G Suite Enterprise all of your users will get this license automatically so you do not need to assign licensed.

If you have multiple user-based subscriptions such as G Suite and Google Drive storage you must assign each user a license. You must also assign a license if you have multiple subscriptions to the same server, e.g: you may have G Suite Business and G Suite Enterprise licenses in your organization.

License assignment can be applied to everyone in your organization, at the organizational unit level ( we will discuss organizational structure later in this course) or at the individual user level. It is also possible to configure automatic license assignment for your organization so you do not need to manually assign a license to each new user.

### Notes
A single user can have a license for more than one service.

## Managing Users Quiz
1. When you delete a user which of the following can be transferred to a new owner?
==R: Calendar Events==

2. What is the behavior for a suspended user? (Choose 2)
==R: A suspend user cannot login to their account
R: Email and new calendar invites are blocked on a suspended users account==

3. How are site-based licenses assigned to users?
==R: Site based licenses are automatically assigned to all users in the organization.==

4. Under what conditions can a forgotten password be recovered by a user?
==R: Only if the administrator has enabled non-admin password recovery.==

5. To allow a user to receive email in their Gmail inbox addressed to multiple addresses you would add?
==R: An email alias.==

# Organizational Structure
## Introduction
Initially all your users are placed in a single organization. All settings you make in the admin console apply to this top-level organization and therefore to all users in your G Suite account.

A single organization can be limiting however so you may want to create an organizational structure by adding organizational units (OUs) to your G Suite account. There are several reasons why you would do this, for example:

To control which applications and services are available to users
To configure the available services differently for different sets of users
You can create as many organizational units as you want, either at the same level or in a hierarchy. Each child OU inherits settings from its parent. Changing a setting at a higher level changes the setting for all child OUs unless you have overridden inheritance and customized settings for the child OU.

A single user exists in one OU only.

In this module you will create two organizational units (OUs) for your company, and place users into each OU according to their job role. You will also learn how to disable a Google service for an individual OU.

==An **organizational unit** is simply a group that an administrator can create in the Admin console to apply settings to a specific set of users. By default, all users are placed in the top-level (parent) organizational unit. Child organizational units inherit the settings from the parent.==

## Create Organizational Units
### Introduction
In this exercise, you will create two OUs and move your users into the appropriate OU based upon their role in the company.

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. From the menu (top left) select **Directory > Organizational units**.

3. Click on the yellow circle with the + sign to create a new OU.

4. Give the OU the name of Executive and click **CREATE**.

5. Create another OU called Employees.

6. Navigate to your users list. You should see the two new OUs on the left hand side beneath the top level organization.

7. Select Alex, Lars, Samantha, and Timothy by checking the box to the left of their name in the user list.

8. Click **More > Change Organizational unit**, and select **Executive**. Then click **CONTINUE**.

9. Click **CHANGE** to confirm the move.

10. Repeat Steps 7 - 9 but this time move Ellie, Jon, Tom, and Will to the Employees OU.

11. Review the options in the column to the left of your user list. Here you can see all users and you can now refine (or filter) the users by OU. Practice filtering by checking **Users from selected organizational units** and picking from the list below to refine the list. Notice how you can pick one or many OUs.

### Notes
Changes can take 24 hours to propagate to all users.

## Restrict Access to a G Suite Service
### Introduction
In the previous exercise you created two OUs beneath your top level organization. One benefit of applying an organizational structure like this is that you can now enable/disable services at an OU level. Settings at one level are normally inherited by any child OUs but it is also possible to override inheritance at the OU level providing for greater flexibility.

Read through the scenario, and then go through the steps to complete the exercise!

### Scenario
You receive this email from the CEO:

Hello G Suite Admin,

Alex advised me of a Google service called Takeout which allows users to export their data from G Suite. Is it possible to enable this service for our executives only but restrict access to our employees? Thanks

Regards,

Sam Morse, CEO

Google Takeout is an additional Google service which is enabled by default for all users in the organization so you must disable the service for all users in the Employees OU.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. From the menu (top left) select **Apps > Additional Google services**.

3. On the left hand side click the **Employees** OU.

4. Scroll down the list of services. Hover over 'Google Takeout' and click on the 3 dots icon at the end of the row. Then click **OFF (Override)**.

5. Click **TURN OFF** to confirm the change. Users in the Employees OU will now lose access to Google Takeout. Users in the root organization and the Executive OU can still use this service.

### Notes
Changes can take 24 hours to propagate to all users.

## Organizational Structure Quiz
1. You want to enable Google+ for your full-time employees but restrict access to your contactors. Which method could be used to do this?
==R: Move the contractors into an OU and turn off Google+ for that OU.==

2. Which of these statements are true about G Suite OUs? (Choose 2)
==R: A G Suite account may contain multiple OUs.
R: A user may belong to one OU only.==

3. How do settings inherit across OUs?
R: Each child OU inherits settings from its parent, which you can then customize.

# Introduction to your Directory
## Introduction
The G Suite directory contains profile information for users in your organization, Google group addresses, plus details of any shared contacts that you add. You can think of it as a global address book.

In addition to names and email addresses, profiles can contain other information such as employee ID, manager details, location, etc. This information helps people find one another, communicate with one another, and understand each others role in the organization. As an administrator, you can add user information and control user visibility in Contacts and other Google services.

When contact sharing is enabled:

- Individual and group addresses autocomplete as users enter them in Google services like Gmail, Google Docs, and Drive.
- Calendar intelligently suggests meeting rooms based on the location and number of guests.
- Users can find profile information in Contacts and other Google services. For example, when users point at or tap someone’s profile photo, they open a person information card.

In this lesson you will explore your directory's sharing and visibility settings. You will also complete a number of exercises where you will allow users to update their own profiles and also create a custom directory for a subset of your users.

## Verify Directory Settings
### Introduction
In this exercise, you will confirm that contact sharing is enabled for your organization.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. From the menu (top left) select **Directory > Directory settings**.

3. Click **Sharing settings**.

4. Ensure that 'Enable contact sharing' is selected. If it is disabled, enable it now.

In this section you can also specify which information is shared. For example, you can choose whether to show or hide email aliases, and if you have multiple domains in your organization you can share the entire directory across all domains or restrict sharing to the domain level only (i.e. users in one domain only see other users in that same domain).

5. Click **SAVE** if you have made any changes.

### Notes

Changes can take 24 hours to propagate to all users.

## Update User Profiles
### Introduction
As an administrator you can add information such as phone numbers, secondary email addresses, and location details to a user's profile. You can edit profiles individually in the admin console or you can use the Admin SDK API or a third party product. You can also use GCDS to update user profiles. Finally, you can also allow users to update some profile information themselves.

In this exercise you will update a user's profile in the admin console. You will then update your directory settings to allow users to update their own profiles.

### Scenario
You receive the following email from Lars Ericsson, the HR Manager:

Hey G Suite Admin,

You may recall that we recently hired Jon Baird. He used to work as a contractor but as he in now full time employee can you please update his job title to be HR Business Partner.

In addition, I understand that G Suite allows users to update some aspects of their own profile. I see no reason why our users should not be allowed to do this so can you please enable this feature. Thanks.

Regards, Lars Ericsson

### Directions
Let's start by updating Jon's job title.

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. Click the **Users** icon.
3. Locate Jon Baird in the list and click his name, then click the **User information** card.
4. Click anywhere in the **Employee information** section. You can now edit this section.
5. Change Jon's Job title to HR Business Partner and click **SAVE**.

Now let's ensure users can update their own profiles.

6. Select **Directory > Directory settings** from the left hand menu.
7. Click **Profile editing**.
8. By default, users can change their 'Birthday' and 'Work location' from their About Me page. Check all other fields so that users can also update their 'Name', 'Photo' and 'Gender'.
9. Click SAVE.

### Notes
It might take up to 24 hours for changes to appear in the directory.

Adding work location information (whether you do this as the administrator or you allow user's to do this for themselves is recommended) is recommended as this allows Google Calendar to make smart room recommendations based upon the user's location. You must also have added your buildings and resources for smart room recommendations to work.

If you decide to complete your employee ID information (and you are not using SSO or 2SV) you can use these IDs as a login challenge to help protect your user accounts when Google suspects that an unauthorized person is trying to access a user’s account.

## Custom Directories
### Introduction
In a single domain environment your organization will have one directory (global address list) and all users can see everyone in that directory. In a multiple domain environment you can restrict visibility such that users in one domain can only see other users in their primary domain.

You can also setup custom directories to limit who users can find in autocomplete lists, contacts, and searches. Custom directories are applied at the OU level.

In this exercise you will create a new OU and configure it to use a custom directory.

### Scenario
You receive the following email from Lars Ericsson, the HR Manager:

Hey G Suite Admin,

We are about to commence a new project and will be installing a new expenses system. A consultant will be joining us for a month or so to help us implement the new system and train our users.

Whilst here he will need to have a G Suite account so we can collaborate on project documents, etc. Can you please create the following account.

![](https://i.imgur.com/JsQ0NzQ.png)

We would also like to keep our company directory information confidential from contract staff so can you restrict visibility so that Mark can only see users involved on the project. Please ensure he can lookup my details and Jon Baird as he will be leading the implementation on our behalf. Thanks.

Regards, Lars Ericsson

### Directions

There are a number of steps you must complete to fully satisfy the request.

==Create a new OU==

Custom directories are applied to an OU so let's start by creating an OU.

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.
2. From the menu (top left) select **Directory > Organizational units**.
3. Click on the yellow circle with the + sign to create a new OU.
4. Give the OU the name of Contractors and click **CREATE**.

==Create the user account==

Now we need to create Mark's account.

5. Click the **Users** icon.

6. Click **Add new user**.

7. In the dialog box that appears, create and account for Mark Jones as follows:
    - First name: Mark
    - Last name: Jones
    - Primary email: mark.jones@yourdomain
    - Organizational unit: Contractors (use the pencil icon on the right to select the correct OU)
    - Password: hellohello1
    - Move the slider for 'Ask for a password change at the next sign-in' to ensure Mark changes his password when he first signs into his account.
8. Click **ADD NEW USER** to create the account.

9. Click **DONE**.

==Create a Google group==

Custom directories use Google Groups to determine which user information to show so we must create a Google group before we create the custom directory.

10. From the menu (top left) select **Directory > Groups**.

11. Click **Create group**.

12. Enter the following Group details:

    - Name: HR Project
    - Description: Custom directory group for HR
    - Group email: hrpoject

13. Click **NEXT**.

14. Choose Team as the access type and click **CREATE GROUP**.

15. Click the **Add members to HR Project** link, then click the yellow circle with a + sign to add members. Enter Mark's email address and also add Lars and Jon.

16. Click **ADD TO GROUP**. You should now see all three users listed as members of the group.

17. Hover over Lars and click the down arrow in the Role column and select **Manager** to make Lars the group's manager.

18. Click **SAVE**.

==Create the custom directory for the new OU==

The final step is to define the custom directory.

19. From the menu (top left) select **Directory > Directory settings**.

20. Click **Visibility settings**.

21. Select **Contractors** from the list of OUs on the left hand side of the page.

22. Change the Directory visibility for the HR Project OU to **Users in a custom directory**.

23. Click **CREATE NEW** and enter a name for the new directory of HR Project.

24. Select HR Project from the list of groups and click **CREATE**.

25. Click **SAVE**.

26. Notify Lars that you have fulfilled his request, and don't forget to provide him with Mark's password.

Congratulations you have just added a custom directory to your organization!

### Notes

It can take up to 24 hours for changes to custom directories to become available.

## Shared Contacts
### Introduction
Your organization's directory will store information about users in your G Suite account but it is very likely that you will deal with users from outside of the organization on a regular basis.

Google provide the Domain Shared Contacts API which allows you to add external contacts your directory. These external contacts will then be presented to your users in services such as Gmail when completing addresses.

In addition to using the API directly to create your external contacts you can also use GCDS. There are a number of third party apps available which will add this information to your directory.

### Notes
Each user can also manage their own personal contacts list where they can add external recipient information.

## Cloud Directory Quiz
1. Users across your organization regularly email your suppliers and would like to have G Suite automatically auto-complete their email addresses in Gmail. What should you do?
R: Use the Domain Shared Contacts API to add these external users to your directory

2. What can you add to a user's profile that can be used by Google as a login challenge when they suspect that an unauthorized person is trying to access a user’s account.
R: Employee ID

3. Where are custom directories defined for a user?
R: In the users OU

4. What settings can a user update by default in their About.me page? (Choose 2)
R: Birthday
R: Work location

# Admin Roles
## Introduction
Administrator roles give a user privileges to manage another user's access to G Suite or to perform actions that affect the setup of your organization's G Suite account. You can make a user either a super administrator with complete access to the G Suite account, or you can assign a role that limits which administrative tasks the user can perform.

## Add a new Super Administrator
### Introduction
In this exercise, you'll grant the 'Super Admin' role to Alex Bell, the IT Manager. This is an example of a pre-built administrator role that's standard on all G Suite accounts.

### Instructions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Users** icon.

3. Locate Alex Bell in the user list and click to enter his account page.

4. Scroll down and select the **Admin roles and privileges** category card. Alex currently has no Admin roles assigned to him.

5. Click **ASSIGN ROLES**.

6. Click the slider for the predefined 'Super Admin' role and then click **SAVE**. You should now see the role has now been assigned to Alex.

Now let’s investigate the specific privileges you have granted to Alex.

7. Return to admin console home page click the **Admin roles** icon.

8. Click the **Super Admin** link on the left to view the current users with this role. At this point, this should only be your initial administrator account, plus Alex.

Each pre-built role has a specific set of privileges assigned to it. Super Admin’s have all privileges to the entire organization. Let’s look at another pre-built role and the privileges that are assigned.

9. Click **Help Desk Admin** and then open the **Privileges** tab and review the assigned privileges. Notice how these administrators have the following 'User' privileges only: 'Read' and 'Reset passwords'.

### Notes
Privileges assigned to pre-built roles cannot be customized.

You can assign an administrator role to a user on the user's account information page, or from the Admin roles page where you define the administrator roles.

When Alex signs in to the admin console, he'll see the default dashboard. 

Any customizations you made are personal to your own administrator account.
Creating more than three super administrators for your domain can affect some recovery options.

## Create and Assign a Custom Role
### Introduction
In this exercise, you will create an admin role that have a custom set of privileges.

### Scenario
You receive a request from the Human Resources Manager, Lars Ericsson.

Hello G Suite Admin,

I would like to understand more about how our users are interacting with G Suite. That way I can create a customized training plan for the company. Is there any way I can run reports that track apps usage and user behaviors?

Regards, Lars Ericsson

You decide that, rather than giving him a pre-built role with privileges he doesn't need, it's best to create a custom role. That way you can delegate the ability to run reports, but not give Lars any other administrator privileges.

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Admin roles** icon.

3. Click **CREATE A NEW ROLE**.

4. Enter a name for the role, e.g: Reporting Role, optionally enter a description, and click **CREATE**.

5. In the **Privileges** tab, you can select the privileges you want users to have with this role. You want this custom role to have reporting privileges only so check the **Reports** box and click **SAVE**.

6. In the previous exercise you assigned the Super Admin role directly to Alex Bell by updating his user profile but you can also assign roles from the Admin roles page. Click **Reporting Role** in the 'User Created Roles' list.

7. Click **ASSIGN ADMINS** (on the Admins tab) and add Lars Ericsson into the Administrators field. Then click **CONFIRM ASSIGNMENT**.

8. Return the user list and locate Lars in the list, then open his profile. You can see here that he has been assigned the new role.

Congratulations! You've now built and assigned a custom administrator role to one of your users, which allows you to better delegate administrator tasks in your domain.

### Notes
You can assign more than one administrator role to a user. Creating multiple roles with fewer privileges is, therefore, more versatile than one role with many privileges. If a user handles multiple tasks, just assign multiple roles.

Assigning a custom role to a user grants them access to the Admin console. The privileges determine which dashboard controls are in their console, what information the user can access, and which management tasks they can perform.

## Administrator Roles Quiz
1. What’s the recommended way to create a custom administrator role for your domain?
R: Create a new role and choose the required privileges.

2. You can assign more than one administrator role to a user.
R: True

3. When assigning an administrative role to a single user, where in the user's account page do you assign the role?
R: Admin roles and privileges

4. Privileges in a pre-built administrator role can be customized.
R: False

# Cancelling your Trial
### Introduction 
As discussed at the beginning of the course, your G Suite trial period lasts for 14 days. At the end of that time you will be charged unless you have cancelled your subscription.

**If you do not intend to take the additional courses** in the G Suite Admin specialization or **if your trial period is about to expire** and you want to avoid charges, you should **cancel your subscription now**.
