# Securing SharePoint List access
When designing this solution we decided to use SharePoint lists as data back end. This is a lightweight approach for data storage that is present in all Office365 without additional licensing. Without any further configuration users may find the SharePoint site and could be able to see or edit information that are not accessible through the app. Here are some hints how to secure the SharePoint lists.
## Using SharePoint Groups
SharePoint is using some predefined groups like "Members" or "Owners". We suggest that you put all users in the "Members" group and administrators in the "Owners" group.
## Basic Security
With some simple modifications you can easily configure a good basic security.
### Securing location tracks
The list btw_locationTrack keeps all check in / check out data. If you want to achieve that users are having access to only their personal data, you can restrict the access accordingly:
- Open the list btw_locationTrack
- Open list settings -> advanced settings
- Set the option _Read Access: Read items that where created by the user_

Now users will have only access to their own tracking records.
### Securing reservation
The list btw_reservation keeps all reservations. The app must have access to all reservations of all users in order to examine which reservations are currently in the system. So users must be able to read every record but edit only their own records. This can be configured by the following steps:
- Open the list btw_locationTrack
- Open list settings -> advanced settings
- Set the option _Create and Edit Access: Create items and edit items that were created by the user_

Now users can only edit or delete their on reservations.
## Advanced Security
With the basic security setting you can avoid that users will have access to personal information by using the SharePoint user interface. For most situations these settings might fit to companies requirements. Here some ideas to implement further security.
### Configuration lists read only
The lists btw_space, btw_shift, btw_site and btw_building are only for configuration by administrators. There is no need for users to edit these lists.
In list settings - advanced settings you may want to set the _Create and Edit access: None_. This prevents users from editing and deleting records in these lists.

For more fine tuning of permissions you might want to define custom permission levels and assign these custom permission levels to your lists. Please refer to the SharePoint manual about this technique or ask a SharePoint consultant.

### Search results
By default list entries in this solution might be shown in search result. To avoid crawling and showing records in search results you go the site settings and than open "Search and Offline Availability" and set the option _Indexing Site Content->Allow this site to appear in search results? = NO_.
### Forms, views and navigation
Yet we did not modify the default SharePoint lists and views. If you want to prevent users to see information that is shown in the default views and forms you might to edit views and forms in order that they only show desired information.
## Summary
As shown above, additional security settings can be configured for the SharePoint lists. For most organizations the basic security settings are sufficient. If more sophisticated settings are needed, SharePoint offers advanced possibilities by setting custom permission levels. Field level security cannot be implemented in SharePoint lists but it is possible to modify forms and views in order to hide fields. If real field level security is desired, it would be necessary to move the data back end to CDS, where also field level security can be implemented.

