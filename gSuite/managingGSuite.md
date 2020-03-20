**Author:** Duarte Matos
###### tags: `G Suite`

# Managing G Suite

![](https://i.imgur.com/o4g942G.png)

## Introduction
You will learn how to enable and disable services and you will also become familiar with the most common settings for core services such as Gmail, Calendar and Drive.

You will also learn the fundamentals of device management with G Suite.

We will introduce you to Google Vault, Google's e-discovery service, the admin reports and dashboards that are available in the admin console, and finally we will take a look at domain management and multi domains with G Suite.

## Prepare your G Suite Domain
### Introduction
This exercise only needs to be completed if the G Suite Enterprise trial domain you used in the previous course 'Introduction to G Suite' has expired. In this case you should create a new domain and populate it as described below:

### Instructions
1. Complete the **Create your G Suite Trial Account** exercise from 'Introduction to G Suite'. You can purchase a new domain or you can use a domain that you already own. Please see the Help Center resource links below for more details on using an existing domain.
2. Create the following OUs:
    - Executive
    - Employees
    - Contractors
3. Create the following G Suite user accounts:

![](https://i.imgur.com/8pFxnPF.png)

4. Complete the Adding Calendar Resources exercise from 'Introduction to G Suite'.

# Managing G Suite Services
## Introduction
This lesson will focus on G Suite services, and how you as a G Suite admin are able to control your users' access to different Google services by enabling and disabling services for different groups. After you get acquainted with how to manage services for your organization, you will then go through the most used services, and the associated best practices for each service.

## Turn Services On or Off for Everyone
### Introduction
As the G Suite administrator, you control user access to different types of Google services, including:

- ==G Suite== which includes enterprise versions of Gmail, Calendar, Drive and Docs, and more. These are the core services that have a Terms of Service agreement and are fully supported by G Suite Support.
- ==Additional Google Services== such as Blogger, Google Books, and more. These services are available to use in G Suite, but aren't covered by the Terms of Service agreement, nor supported by G Suite Support.
- ==Marketplace apps==. The G Suite Marketplace lets administrators browse for, purchase, and deploy integrated, business-oriented cloud applications. Warranties and support for these third-party apps are provided by the vendor, but not G Suite Support.

Administrators can turn services on or off for the entire organization or for a particular OU. In this exercise, you'll learn how to configure services to fit your company's business needs.

==All settings you make in the Admin console apply to this top-level organization and therefore to all users and devices in your account.==

### Scenario
Your company has a strong focus on the confidentiality of their corporate information. As the administrator, you've been asked by the IT Manager to remove the ability to access some Google services to align better with their business policy.

Hey G Suite Admin,

As you know we are working on a very confidential widget at the moment. To prevent any information leaks I don't want anyone able to create a blog or site with their company account.

Thanks, 

Alex Bell, IT Manager

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com. 

2. Click the **Apps** icon.

3. Click **G Suite**.

4. Sites is a core service and core services are generally enabled for everyone by default. To turn off this service, locate Sites in the list and click the ellipses (three vertical dots) icon at the end of the row. Then click **Turn OFF for everyone**.

5. Click **TURN OFF** to confirm.

6. Verify that the Sites service has been disabled. There are two ways to do this.

    - Click the Sites link to enter the service’s settings page. Then click the URL below the service title. This option is available for most services in the admin console.
    - Open a new browser tab and go to https://sites.google.com/a/yourdomain .When you try to access the Sites service you should see a message advising that you do not have access to that service.

7. You must now turn off Blogger as per Alex's request. Blogger is an additional service so from the admin console click **Apps > Additional Google services**.

8. Locate Blogger in the list and click the ellipses (three vertical dots) icon at the end of the row. Then click **Turn OFF for everyone**.

9. Click **TURN OFF** to confirm.

You've successfully turned off the two services for your whole organization.

### Notes
It can take up to 24 hours for a service ON/OFF change to take effect.

Some services depend on other services. For example, Google+ depends on Calendar, Drive, and others. You can't turn on Google+ services, unless the other services are also on.

## Enable/Disable a Service for a Single OU
### Introduction
In the previous exercise you disabled two services for your entire organization. In this exercise you will enable and disable a service at the OU level.

### Scenario
Your receive the following email from Alex.

Hey G Suite Admin,

Thanks for turning off those services for me. However, our CEO has advised me that they will want to create a site at some stage so can you enable the Sites service for our executive only?

Also, can you turn off Google+ for all contractors?

Thanks, 

Alex Bell, IT Manager

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com. 

2. Click the **Apps** icon.

3. Click **G Suite**.

4. Click on the **Executive** OU (left side of the page). You are now viewing the status for Apps in the Executive OU only. Note that Sites is OFF at the moment as it inherits it's setting from the top level organization.

5. To turn Sites on for this OU only, locate Sites in the list and click the ellipses (three vertical dots) icon at the end of the row. Then click **ON (Override)**.

5. Click **TURN ON** to confirm. The Sites service status should change to ON.

6. Click another OU and/or the top level organization and verify that the Sites service remains OFF for other parts of the organization.

7. Click on the **Contractors** OU.

8. Locate Google+ in the list and click the ellipses (three vertical dots) icon at the end of the row. Then click **OFF (Override)**.

9. Click **TURN OFF** to confirm. You may need to confirm a second time. If prompted, click **TURN GOOGLE+ OFF**.

You've successfully turned a single service on and another one off at the OU level thus overriding inheritance from the higher level organization.

### Notes
It can take up to 24 hours for a service ON/OFF change to take effect.

## Enabling a Service Using Groups
### Introduction
In the previous exercise you learned how to enable and disable a service for an individual OU. This alignment between service status and organizational structure is very useful but what happens if you want to enable a service for some users in an OU but keep it disabled for others. In this exercise you will learn how to enable a service for specific users by leveraging a Google Group.

### Scenario
Your receive the following email from Alex.

Hey G Suite Admin,

Sam, our CEO would like to enable Sites for here Executive Assistant Ellie Gray. Can you please do that for her.

Thanks, 

Alex Bell, IT Manager

### Directions

1. Open a new incognito browser window and go to mail.google.com.

2. Sign in as Ellie Gray *ellie.gray@yourdomain*

3. Navigate to *https://sites.google.com/a/yourdomain* to confirm that Ellie does not have access to the Sites service.

4. Sign out and sign back in to your domain as the administrator at admin.google.com. 

You are now going to create a group and make Ellie a member. Then you will enable the Sites service for this group.

5. Click the **Groups** icon.

6. Click **Create group** and enter the following information:
    - Name: Access Sites
    - Description: Users with access to the sites service regardless of their OU setting
    - Group email: access.sites@yourdomain

7. Set the 'Access type' to *Restricted* (Only members can post and view topics)

8. Click **CREATE GROUP**.

9. Click the **Add members to Access Sites** link and add Ellie Gray as a member.

Now we will enable Sites access for the group created above.

10. Navigate to the **Apps > G Suite**.

11. Click the Groups link on the left hand side of the page.

12. Add *Access Sites* to the 'Search for a group' field. The right hand side of the screen will now show status for apps in Access Sites.

13. Locate *Sites* in the list of services and hover over the row, then click **TURN ON**.

14. Click **TURN ON** to confirm.

Verify that Ellie can now access the Sites service.

15. Sign out as the domain administrator and sign back in as Ellie.

16. Navigate to *https://sites.google.com/a/yourdomain*.

Even though Ellie's OU has Sites disabled, the sites page should load because she is a member of the access group with Sites enabled

### Notes
It can take up to 24 hours for a service ON/OFF change to take effect.

Groups turn on user access to G Suite core services and Google additional services (such as App Maker). Groups can’t turn off user access to a service that’s turned on for an organization.

It's a good practice to develop a naming convention for access groups such as the one create in this exercise, e.g. prefix the group name/email with Access or AX.

An access group can contain users from any organizational unit or another group (nested groups).

## Set Services Release Track
### Introduction
G Suite is 100 percent web, so your users receive new features and updates automatically, without needing to install or update any software. However, you can still control when new features become available for users.

Setting which release track your company is on is an important administration task. It defines when new features and updates are applied in your domain.

To help make that decision, you can choose from:
- ==Scheduled release track==: (Recommended and enabled by default) Choose this track to delay releasing new features to users, giving you extra time to train your support staff and prepare users for the coming changes. Google releases features to the Scheduled Release track on Tuesdays only, at least one week after the feature was released to the Rapid Release track.

- ==Rapid release track==: Choose this track if you want users to access new features as soon as Google rolls them out to consumer users. These features have been through testing and quality assurance, but users will see them at the same time you do, before you have a chance to evaluate them for your organization.

### Directions

1. Review the G Suite release calendar to see which features are currently on the Rapid Release track. As the administrator, you should be aware of new changes; Rapid Release are marked in red.

2. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

3. Click the **Company profile** icon.

4. Click **Profile**. You can select domain wide settings using the Profile feature.

5. In the 'New User Features' section, select the Rapid release option.

6. Click **SAVE**. Your users will now have access to new user features as soon as Google releases them.

### Notes
It may take up to a day for changes to take effect.

## G Suite Services Quiz
1. For a domain that has implemented an organizational hierarchy, at what levels can G Suite services such as Sites and Gmail be turned on or off? (Choose 2)
==R: At the organization level
R: At the OU level==

2. Which four of these apps are G Suite core services that are covered in the G Suite Terms of Service? (Choose 4)
==R: Google Drive, Google Talk/Hangouts, Google Calendar, Google+==

3. What is the correct pathway in the admin console to getting to G Suite's core services list?
==R: Admin Console > Apps > G Suite==

4. All Additional Google services are turned ON by default.
==R: False==

# Gmail
## Configure Common User Settings
### Introduction
In this exercise you will check and configure some of the more common user settings for your organization. You will also modify settings for a single OU as per company policy.

### Scenario
The company has decided to configure several important Gmail features and user access settings as follows:
- Let users choose their own themes
- Don't allow email read receipts to be sent
- Let users delegate access to their mailbox to other users
- Enable Gmail web offline
- Do not allow contractors to delegate access to their mailbox or use Gmail web offline

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Gmail** service.

3. Click **User settings**.

4. Review the settings for Gmail. Several policies are already configured while others must be changed.
    - In ==‘Themes’== ensure Let users choose their own themes is checked.
    - In the ==‘Email Read Receipts’== section ensure Do not allow email read receipts to be sent option is selected.
    - In the ==‘Mail Delegation’== section check the Let users delegate access to their mailbox to other users in the domain box.
    - In the ==‘Gmail web offline’== section check the Enable Gmail web offline box.

5. Click **SAVE**.

6. Click the **Contractors** OU (left side of page).

Note the OU policies are inherited from the top level organization:
- In the ==‘Mail Delegation’== section deselect the Let users delegate access to their mailbox to other users in the domain box.
- In the ==‘Gmail web offline’== section deselect the Enable Gmail web offline box.

7. Click **Save**.

## Enable Gmail Labs
### Introduction
While Gmail Labs are experimental, the company has decided to enable this feature for all their users. They may decide to only enable certain labs later, but have decided to see how users respond to the labs first. Complete the instructions below to verify labs are enabled for the organization.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Gmail** service.

3. Click **Labs**. Note that labs are enabled by default.

4. Check the *Advanced Labs Management box* and explore the options. Optionally, you can also disable labs entirely for your users.

5. Click **DISCARD**.

## Enable G Suite Sync for Executives
### Introduction
In this exercise you will check and configure end user access to Gmail as per company policy.

### Scenario
The company wants to restrict the use of ==G Suite Sync for Microsoft Outlook (GSSMO)== to the executive only. You must ensure that only users in the Executive OU can use GSSMO.

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Gmail** service.

3. Click **End User access**. You may need to scroll down to see this section.

4. Click on your top level organization on the left and ensure that =='POP and IMAP access' is set to OFF==.

5. Click on the G Suite Sync row and ensure Enable G Suite Sync for Microsoft Outlook for my users box is deselected.

6. If you made changes, click **SAVE**.

7. Now click the **Executive** OU.

8. Click on the G Suite Sync row and check the Enable G Suite Sync for Microsoft Outlook for my users box.

9. Click **OVERRIDE** (you are overriding the inherited setting from the top level organization).

## Configure Compliance Policies
### Introduction
We will be covering Gmail's advanced settings in a later course in the series, but as an introduction, in this exercise you will set a couple of compliance policies for your organization.

==Simply put, corporate **compliance** means having internal **policies** and procedures designed to prevent and detect violations of applicable law, regulations, rules and ethical standards by employees, agents and others. It involves legal risk management and internal controls.==

### Scenario
G Suite provides a rich set of email compliance policies you can configure for an organization or the entire domain. The IT Manager has decided to follow Google's best practices to configure only a few compliance policies to start and possibly add more later.
- The company will continue to use their compliance footer which will be appended to the end of all email message leaving the company, but not for internal messages.
- The company also wants to prevent their users from receiving attachments that are video, multimedia and music from external users. G Suite can remove these attachments, yet deliver the message. For now, these file attachments can be sent internally between employees. They may revisit this policy later.

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Gmail** service.

3. Scroll down and click **Advanced settings**.

4. Scroll down to the =='Compliance'== section and hover over the =='Append footer'== row, then click **CONFIGURE**. The ==‘Append footer’== dialog box displays.

5. Enter a short description that will appear within the setting's summary, such as Company compliance footer.

6. Enter (or copy and paste) the compliance footer as follows into the ‘For all outbound email messages, append the following footer’ field:

This message (and any associated files) may contain confidential and/or privileged information. If you are not the intended recipient or authorized to receive this for the intended recipient, you must not use, copy, disclose or take any action based on this message or any information herein. If you have received this message in error, please advise the sender immediately by sending a reply email and delete this message. Thank you for your cooperation.

7. Optionally modify the text by changing the font size and style.

8. Click **ADD SETTING**.

9. Click **SAVE**.

You will now configure a compliance rule to strip video, multimedia and music attachments from all inbound messages.

10. Scroll down and hover over the 'Attachment compliance' row, then click **CONFIGURE**. The 'Attachment compliance' dialog box displays.

11. Enter a short description that will appear within the setting's summary, such as Remove video and music attachments.

12. In the =='Email messages to affect'== section, check the Inbound box.

13. Under 'Add expressions that describe the content you want to search for in each message', click ADD, then select Video and multimedia and Music and sound as the type of attachments.

14. Click **SAVE**.

15. In the 'If the above expressions match, do the following' section, ensure Modify message is selected and check the Remove attachments from message box. Note how you can optionally append a message to notify recipients that attachments have been removed.

16. Click **ADD SETTING**.

17. Click **SAVE**.

18. Verify the above policies:

- Send an email from your training account to your personal email. Does it include the compliance footer?
- Reply to the email and attach a video or music file. Does the training account user receive the message with the attachment?

## Gmail Quiz
1. Which of the following settings cannot be set from the Gmail service settings?
==R: Default language==

2. Which of these settings are controlled by the users from their Gmail settings? (Choose 2)
==R: Display language for the gmail interface
R: Add POP3 accounts to the user's inbox==

3. In order to allow users to add experimental, pre-release features to their Gmail, what do you need to enable?
==R: Gmail Labs==

4. Which of the following actions can be taken on a message when an attachment compliance rule is matched? (Choose 3)
==R: Modify message, Reject message, Quarantine message==

# Calendar 
Calendar is an extremely important core service that is offered as part of G Suite. Users are going to want to set up their calendars as soon as possible. This lesson will take you through how to administer the Calendar service. Ensure that you explore the Help Center resources.

## Set Calendar Sharing Settings
### Introduction
In this exercise you will review the sharing settings for the Calendar service.

### Scenario
The company wants to restrict external sharing of calendars but also allow internal sharing to be managed by each user. Users can:
- Only share free/busy information publicly
- Share all information internally

### Directions

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Calendar** service.

3. Click **Sharing settings**.

4. Confirm that =='External sharing options for primary calendars'== is set to Only *free/busy* information (hide event details). This represents the highest level of sharing allowed.

5. Confirm that =='Internal sharing options for primary calendars'== is set to *Share all information*. This represents the default setting for new users. Users can still change this setting.

6. Return to the Calendar settings page, scroll down and click **General settings**.

7. Confirm that 'External sharing options for secondary calendars' is set to Only free/busy information (hide event details). This represents the highest level of sharing allowed.

8. Confirm that 'Internal sharing options for primary calendars' is set to Share all information. This represents the default setting for new calendars. Users can still change this setting.

### Notes

The sharing settings you set above determine the highest level of sharing that a user is allowed to make for their calendars.

If you lower a 'highest level of sharing' setting people may lose access to calendars they could see previously.

## Configure Access to Calendar Resources
### Introduction
In an earlier exercise you created two calendar resources: Conference room, and Boardroom. By default, no-one should be able to book the resources except administrators.

This exercise will guide you through setting access to both of these resources. Read through the scenario and then complete the steps in the exercise. Remember, if you feel you need more context, go back to the help center resources linked at the beginning of this lesson.

### Scenario
You have received a request from Alex, IT Manager asking you to allow anyone in the organization to be able to book the Conference room but he also wants you to restrict booking access for the Boardroom to the Ellie Gray only. As Executive Assistant only she should be able to manage this resource.

The Boardroom should have restricted access to the Executive Assistant.

### Directions

In G Suite, calendar resources are owned by the administrator users, which means you manage the settings of these calendars resources from your own calendar.

1. Sign in as the administrator and open your Google Calendar from the Apps launcher or by visiting calendar.google.com

Eventually the calendar resources will automatically appear in the administrator's 'My calendars' list. This can take some time however so if necessary, we'll use another technique to make them display sooner. If you cannot see the Boardroom under 'My calendars':

- Click the + sign to the right of 'Other Calendars' and click **Browse resources**. You should see the Boardroom listed.
- Hover over the Boardroom and tick the check box to the right of the resource. Repeat this for the Conference room.
- Go back to your calendar. Both resources should now be listed under 'My calendars'.

==Make the Conference room available for all users==

2. Hover over the Conference room in your 'My calendars' list and click the ellipses (three vertical dots) next to the calendar name, and then click **Settings and sharing**.

3. Adjust the sharing settings as follows:

    - In the 'Access permissions' section, check the Make available for yourdomain box. By default they should be unchecked.

4. Return to your calendar. Hover over the Boardroom in your 'My calendars' list and click the ellipses (three vertical dots) next to the calendar name, and then click **Settings and sharing**.

5. Adjust the sharing settings as follows:

    - In the 'Access permissions' section, ensure that Make available to public and Make available for yourdomain are both deselected.
    - In the 'Share with specific people' section, click **Add people** and add Ellie Gray.
    - Set her Permissions to 'Make changes and manage sharing' and click **Send**.

6. Verify that the Boardroom is available to Ellie and not available to other users.
    - Sign in as Ellie and open Google Calendar. You should see the Boardroom listed under 'My Calendars'. You won't see the Conference room listed because you do not manage this calendar.
    - Create an event. You should see both rooms listed on the 'Rooms' tab. Note: You manage the Boardroom but you can also see the Conference room because this was made available to all users in Step 3 above.
    - Sign out and sign in again, this time as Jon Baird and open Google Calendar.
    - Create an event and look at the 'Rooms' tab. You should see the Conference room only. You do not have access to book the Boardroom so it will not be listed.

7. Optionally, try to subscribe to the Boardroom as Jon by browsing to the resource and checking the box to the right of the resource name in the 'Resources' list. This should result in an error as Jon does not have access.

## Calendar Quiz
1. Which Calendar settings can an administrator control for everyone in the organization? (Choose 2)
==R: Highest level of external sharing for primary calendars.
R: Default level of internal sharing for primary calendars.==

2. What are Calendar Resources? (Choose 2)
==R: Bookable equipment
R: Bookable conference rooms==

3. What can users control when it comes to their Calendar?
==R: Users control what they share internally==

4. What are recommended to be configured before adding resources to the organization? (Choose 2)
==R: Features
R: Buildings==

# Drive and Docs
In these exercises, you'll learn how to configure Google Drive for your domain.

You will learn how to control the document visibility and sharing, transfer ownership, and restore deleted files. We will also discuss backup and sync options.

Finally we will take a look at Shared drives (formerly known as Team drives), a shared space where your teams can easily store, search, and access their team's files anywhere and from any device.

## Drive Sharing Settings
### Introduction
Google Drive is a way for your users to access and share all their files, folders, and Google documents at any time and on any device.

As the administrator, you determine whether users can share their documents outside your organization, whether they can access documents created outside your organization, and the default visibility level for new documents.

### Scenario
You receive the following email from Sam Morse:

Hello G Suite Admin,

I have been thinking about how I want our people to share documents inside and outside the company. I want everyone to be able to share documents with our clients and partners, but not be able to publish openly on the web.

I also want to build a strong collaboration culture, so inside the company I want everyone to be able to have permission to see each others documents but only if they have the link first. Can you make this happen?

Regards,

Sam Morse, CEO

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Drive and Docs service**.

3. Click **Sharing settings**. The current settings display for your organization.

4. Sam wants users to be able to share outside the organization, but does not want users to publish anything to the web. To achieve this, click **Sharing options** to edit the settings.

5. Set the 'Sharing outside of yourdomain' field to ON. Files owned by users in your organization can be shared externally. This setting applies to shared drives as well.

6. Deselect the check box for 'Allow users in yourdomain to publish files on the web or make them visible to the world as public or unlisted files'.

7. Click **SAVE**.

8. Sam also wants users to collaborate internally through sharing links so scroll down the Drive and Docs service settings page and click on **Link Sharing**.

9. The default setting for this option is OFF. To change the file visibility so that anyone in the company can access a document once they have the link, select ON - Anyone at yourdomain with the link.

This option is recommended for two reasons:

- Allows for easy sharing, but offers protection from outside the organization, because users must sign in to access the shared documents.
- Documents with this visibility won't normally be found in search results.

10. Click **SAVE**.

### Notes
In the sharing settings area you may also have seen an option to allow sharing with whitelisted domains. This is very useful if your partners/customers have compatible domains as you can allow external sharing but restrict it to a names set of domains.

Sharing settings discussed here override shared drive external sharing settings. If you disable sharing outside of your organization, manager of shared drives cannot override this setting even if they are allowed to change shared drive settings.

## Transfer Ownership
### Introduction
As the administrator you can transfer all documents owned by one user to the another user in your organization.

There are three user types in Google Drive: owner, editor, and viewer. Documents can have many editors and viewers, but only one owner at a time.

By *default*, ==the creator of a document is also the owner, but document ownership can be transferred to another user==. After the transfer, the original owner retains editing privileges of the documents unless that user is deleted or their edit permissions are removed.

We've already seen that transferring ownership of a user's documents can be useful when the user leaves the organization. When you delete a user from the admin console you are given the option to transfer files, calendar and Google+ pages to a new user. And it's good practice to transfer ownership to avoid losing important documents.

Note that documents owned by a deleted user can't be transferred. However, if the user was deleted less than 20 days ago an admin can restore the user's documents and then transfer those documents.

### Scenario
You receive the following email from Sam Morse:

Hello G Suite Admin,

My executive assistant, Ellie, is responsible for maintaining many of my important documents. Is there a way that I can make her the owner so that she has total control over them, while still allowing me to make changes?

Regards,

Sam Morse, CEO

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Drive and Docs** service.

3. Click **Transfer ownership**.

4. Enter samantha.morse into the 'From' field and ellie.gray into the 'To' field.

5. Click **TRANSFER FILES**. You should now see a prompt advising that you, the old owner and the new owner will receive and email upon completion of the transfer. Click **OK**.

6. Open your inbox and verify that you have received a confirmation email.

### Notes
It's also possible to transfer ownership of documents using the Drive API.

## Restore Deleted Files
### Introduction
There comes a time in every administrator's job where someone will approach you, in a panic and desperate to recover lost data. The good news is that G Suite has a way for you to restore a user's data for a certain period of time.

You can restore a user's deleted Google Drive files for a date range you specify, as long as the files were deleted within the past 25 days. This helps ensure that, if a user accidentally deleted important files, those files are not permanently lost.

In this exercise you will log into as a G Suite user, create a file and then delete it. You will then restore that file as the administrator.

### Scenario
You receive the following email from Timothy:

Hey G Suite Admin,

I don't know how it's happened, but a really important finance report ("Super Important Budget") has vanished. It's gone. Even if I search, I can't find it, but it was there 3 days ago. It would take months of work to recreate it. I emptied the trash yesterday; it must have been in there somehow. Can you please help?!

Thanks

Timothy Lee, Finance Manager

### Directions
==Permanently delete a file==

1. Sign into G Suite as Timothy Lee at drive.google.com.

2. Create Google sheet named Super Important Budget. Close the sheet. This will take you to your 'My Drive'.

3. Drag the sheet to the Bin on the left, or right click on the sheet and click **Remove**.

4. Open the Bin. You should see the sheet you just deleted. Now click the **Empty bin** link. Alternatively, right click on the sheet and click Delete forever.

5. Click **EMPTY BIN** or **DELETE FOREVER** to confirm.

==Recover the deleted file==

6. Sign out of G Suite and sign back in to your domain as the administrator at admin.google.com.

7. Click the **Users** icon.

8. Locate Timothy Lee in the list and hover over his name, then click **More > Restore Data**.

9. A dialog box will now be presented where you can enter a from and to date range. Complete the date values and ensure that 'Application' is set to Drive. Then click **RESTORE**.

==Verify the file has been restored==

10. Repeat Step 1 and sign into Drive as Timothy. You should see the Super Important Budget file in Timothy's My Drive.

## Enable Docs Offline Access
### Introduction
Through offline access users are able to view and edit Google documents, spreadsheets, and presentations even when they don't have an Internet connection. As the administrator, it's important for you to know the options and limitations of Drive offline access.

### Scenario
You receive the following email from Sam:

Hello G Suite Admin,

I'm traveling next week but need to prepare for a meeting. I've been told that I can have offline access to my documents in Drive even when I'm on the plane. I mostly want to view and edit presentations and spreadsheets.

Can you look into it for me? I'll have my Windows laptop with Firefox with me. How do I set it up?

Thanks

Sam Morse, CEO

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Drive and Docs** service.

3. Click **Features and Applications**.

4. Click **Offline** to edit the offline settings.

5. Ensure that Allow users to enable offline access (recommended) is selected.

6. Click **SAVE** if you made changes in the previous step.

Sam can now enable offline access to Docs.
- Can Sam use Firefox to access her docs offline?
- What app does Sam need to install?
- What steps will Sam have to take to have offline access for her trip?
- How can Sam view the docs once offline?
- Can Sam edit the docs she wants to use on the flight?
- If Sam has another device, is it set up automatically?

7. You should now advise Sam of the steps she needs to take to complete the offline configuration. An example email is below:

Hey Sam,

I've looked into offline access for you. You must download and install the Chrome browser and offline extension on your laptop. Instructions can be found here to setup offline access - Work on Google Docs, Sheets, & Slides offline. It should only take a minute.

Once you've enabled offline access to view your files when traveling, open Chrome and visit drive.google.com. The offline version of your Drive will load. Then you can then view and edit your presentations & spreadsheets without an Internet connection.

Additionally, if you want offline access on other devices, you need to set this up on each device individually.

Please let me know if you have any questions.

Regards,

G Suite Admin

## Stream or Sync Files
### Introduction
There are two ways to access Drive files and keep them in sync on all your devices.

**Drive File Stream** which is best for most organizations. This application lets you stream My Drive and shared drive files directly from the cloud. You can also make Drive files available for offline access.

**Backup and Sync** which is Google's consumer sync client that organizations can use, too. With Backup and Sync, all your Drive content is stored locally.

In this exercise, you will enable the use of Drive File Stream and allow users to install the software themselves.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Drive and Docs** service.

3. Click **Features and Applications**.

4. Click **Drive File Stream** to edit the settings.

5. Check the 'Allow Drive File Stream in your organization' and 'Show Drive File Stream download link' boxes. The second box allows users to install Drive File Stream from the Settings menu in Drive.

6. Click **SAVE** if you made changes above.

7. Go to drive.google.com and click the Settings menu (the gear icon). Verify that there is a 'Get Drive File Stream' option. Note: If you made changes in Step 5 you may need to wait some time for the link to appear.

### Notes
You can allow Drive File Stream and Backup and Sync for your users. If a user runs Drive File Stream at the same time as Backup and Sync, the user is prompted to stop syncing My Drive in Backup and Sync. If they agree, they will now access My Drive only with Drive File Stream which frees up disk space and improves performance. If they decline they continue to use both products which nullifies disk space savings and potentially leads to confusion.

If you enable the download links for both tools, only the Drive File Stream link is presented.

## Shared Drive Creation
### Introduction
Shared drives are shared spaces where teams can easily store, search, and access their files anywhere, from any device. Unlike files in My Drive, files in a shared drive belong to the team instead of an individual. Even if members leave, the files stay exactly where they are so your team can continue to share information and get work done.

In this exercise you check that shared drive creation is enabled for your organization and you will modify settings to ensure data remains confidential only to members of each drive.

### Scenario
You receive the following email from Sam Morse:

Hello G Suite Admin,

As you know we have quite a few ongoing projects and have people join and leave those projects on a regular basis. I would like for us to be able to store project documents in a shared space so users do not need to keep these files in their personal Drive and share them with others manually.

Can you please confirm that all users can create shared drives as they require them. I would also like to ensure that shared drive files cannot be accessed by external user and non members of the shared drive but allow the shared drive owner discretion on that point.

Can you make this happen?

Regards,

Sam Morse, CEO

### Directions
Let's start by setting the shared drive policies.

1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Drive and Docs** service.

3. Click **Sharing settings**.

4. Click **Shared drive creation** and configure the settings as follows:
- Prevent users in yourdomain from creating new shared drives. Unchecked.
- Prevent full-access members from modifying shared drive settings. Unchecked.
- Prevent people outside yourdomain from accessing files in the shared drive. Checked.
- Prevent non-members of the shared drive from accessing files in the shared drive. Checked.
- Prevent commenters and viewers from downloading, copying and printing files in the shared drive. Unchecked

5. Click **SAVE**.

Now we will create a shared drive.

6. Sign out and sign back into G Suite as Timothy Lee at drive.google.com.

7. Click **Shared drives** on the left, and click **CREATE SHARED DRIVE**.

8. Enter a drive name, e.g. Project X and click **CREATE**.

9. Click the **Add members** link and add Sam Morse as a Content Manager, then click **SEND** to send here a notification that she has been added to the shared drive.

10. Click on the shared drive title to reveal a drop down menu, and select **Shared drive settings**. Note that you can modify the external and non-member settings. This is because the policy above allows full-access members to modify shared drive settings.

11. Optionally, sign back in as the administrator and return to the Sharing options card. From here disable sharing outside of the domain. Then sign back in as Timothy Lee and check the shared drive settings again. You should see that sharing outside of the domain is now disabled and cannot be changed. This is because the Sharing options override and apply to shared drives.

## Explore Shared Drive Management
### Introduction
As the administrator you have visibility and can manage all shared drives in your organization.

In this exercise you will explore the management features offered to you in the admin console.

### Directions
1. If you are not already signed in, sign in to your domain as the administrator at admin.google.com.

2. Click the **Apps** icon, click the **G Suite** icon and then click the **Drive and Docs** service.

3. Click **Migration settings**. From here you can control if your users can migrate content into a shared drive.

4. Return to the Drive and Docs service settings and click **Manage shared drives**. From here you can see an manage all shared drives in your organization. You can:
    - Manage members
    - Manage shared drive settings. Note: You can also override the policy that allows full-access members to manage shared drive settings from here at the individual shared drive level.
    - Restore a drive or data to a team drive

5. Hover over the shared drive that Timothy Lee created in the previous exercise and click the **Settings** icon (gear) on the right hand side of the screen.

6. Check the 'Prevent full-access members from modifying shared drive settings' box and click **DONE**.

7. Sign out and sign back into G Suite as Timothy Lee at drive.google.com.

8. Click **Shared drives** on the left, and open the shared drive created in the previous exercise.

9. Click on the shared drive title to reveal a drop down menu, and select **Shared drive settings**. Note how you can see the settings but you can no longer change any of them.

### Notes
1. If you allow users to migrate content to a shared drive, they must have edit access on the files they wish to migrate, and the owner of the files must be a member of the destination shared drive.

## Drive and Docs Quiz
1. Your company wants to implement the policy that new documents will be shared internally with everyone in the company. This way users won’t have to explicitly share new documents with others. What’s the recommended way to set this up?
==R: Change Link Sharing Defaults to "ON - Anyone at your organization with the link"==

2. Your company allows external sharing of documents but your CEO is concerned about how documents are shared externally. As the administrator, which additional protections might you put in place? (Choose 2)
==R: Require a Google sign in when viewing a shared file
R: Enable the feature that warns users when sharing outside the organization.==

3. A user left your company last month and you deleted their G Suite account 15 days ago. You have been contacted as the administrator and asked if you can recover the deleted user's documents, What should do?
==R: Restore the user, transfer the files to new owner, and delete the user again.==

4. From which places can you transfer file ownership from one user to another? (Choose 2)
==R: When deleting a user from the admin console
R: From the Drive and Docs service settings page==

5. What actions can you take as administrator from the Managed shared drives area in the admin console? (Choose 3)
==R: Restore a deleted drive or files, Manage shared drive sharing settings, Manage members.==





