![[Pasted image 20250303151615.png]]

> [!Three Key Concept of Data related in Salesforce] 
> 1.  Objects 
> 2. Fields 
> 3. Records

![[Pasted image 20250303152802.png]]

![[Pasted image 20250303153116.png]]


![[Pasted image 20250303153023.png]]

> There are three key constructs related to data in Salesforce: ==**objects, fields,**== and **==records==. ==Objects==** are similar to tables in databases. **==Fields==** are similar to columns of the table. **==Records==** are similar to rows of data inside the table. Salesforce uses object-level, field-level, and record-level security to secure access to object, field, and individual records.

## Object-level-security

## Layer 1: Object-level-security

Before allowing a user access, Salesforce first verifies that the ==user has permissions== to see objects of that type. Object-level access can be managed through ==two configurations, profiles and permission sets.==

### 1.1 Profiles

> [!NOTE]
> In Salesforce, profiles have historically been the way to control access to object-level and field-level security. However, since permission sets were released, ==we recommend to use them as the primary way to configure object and field permissions, together with permission set groups==. ==Note that assigning each user a profile is still compulsory==, as this is the place where you configure other things like page layout assignments or login IP restrictions. However, for object and field security setup, configure profiles for minimum access and use permission sets and permission set groups to add permissions.

### 1.2 Permission sets and Permission Set Groups

Since Maria is a new employee, an admin needs to assign Maria to the appropriate permission sets that grant her access to the sales apps and related objects.

> [!IMPORTANT]
> We recommend permission sets as the primary way to assign object and field permissions. Here’s why:
> 
> - They are more flexible.
> - They are packageable.
> - They are upgradeable too.
> 

While packageability and upgradeability are self-explanatory, let’s look at how permission sets and permission set groups are more flexible. In contrast to profiles, you can add multiple permission sets to a given user. This gives you much more flexibility at the time of designing your security model, as functionality can be grouped in more granular ways. When only using profiles, you needed to group all the object and field permissions in a single profile, for instance for a concrete job role, as sales exec. With permission sets you can have different permission sets representing the different tasks that that a sales exec performs: manage leads, approve opportunities, etc. and add or remove smaller chunks of permissions to a user at any time.

Because of the granular nature of permission sets, you can end up with lots of permission sets in your organization. To manage them in a simpler way you can group them in permission set groups. That way, Maria can be assigned a permission set group in one action. This means the grouped permission sets are summed into the permission set group and assigned to Maria as a single artifact.
