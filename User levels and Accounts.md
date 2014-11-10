# User levels

_This is a **draft** document._
_Proposed structure_

There are 2 User levels, each with different permissions on the platform (Entire site).

Below is a detailed description of the proposal.

Level | Permissions
-------------|--------|------------
Steward | 0 1
Non steward | 1

List of all the permissions for the above levels.

Number | Details
-------|--------
0 | [Create, Edit, Remove, View] Users, Consumers, Campaigns,Programs, Brands
1 | [Edit] Personal account, [View] All users

Stewards will have full read and write access to everything on the site.
That is, they can delete, view and add anything.
They can assign brands and accounts to other users

While Non stewards will only be able to edit their own profiles, but cannot add accounts for themselves.
Non stewards will only be able to create and edit campaigns depending on the account level they have for a particular brand.
This means, when the user logs in, their "Steward" level needs to be returned, plus their account role per brand as part of their brands list.
This then determines if a user can archive or activate Programs or campaigns.

When a user logs in the following is the proposed returned structure.
Focusing on the role under "user" and the roles under "brands"

{"securitytoken":"54d79452-a831-4b83-bffe-1bc1e9fe42b7",
"status":"200",
"user":{
    "brands":[
        {
        "id":"469bbea6-2532-4bf1-84b2-af656da10325",
        "name":"Kotex",
        "role":"1"}
        ,{
        "id":"40c03869-6424-4fab-b56a-797eb603e7fa",
        "name":"Baby Soft",
         "role":"3"}
        ],
    "companies":[
        {"id":"516A1A7A-2C2G-3A0A-A55A-71A09643E94B1",
        "intId":1,
        "name":"Kimbery Clark",
        "roleId":3
        }],
    "display_name":"Rowan Deysel",
    "email":"emmanuel@codecafe.co.za",
    "firstname":"Rowan",
    "id":"0248b1e7-da23-4319-bfa3-d1ea4be47786",
    "lastname":"Deysel",
    "mobile":"0714409713",
    "photo_url":"https:\/\/bbb.com\/rowanface.jpg",
    "role":"3",
    "title":"Genius"
    }
  }

