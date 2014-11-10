# User levels

_This is a **draft** document._

> Users have platform access, and each User will have an 'Account' (read: user role) **per brand**.

Only specific Users should be allowed to administrate other Users and their relevant 'Accounts'.

This means that each User needs access control. We don't want a User to be able to give themselves admin access from the Users' screen.

Therefore, **2 _User_ 'levels' should be created.**

Below is a detailed description of the proposal.

Level | Permissions
-------------|--------|------------
Steward | 0
Non steward | 1

List of all the permissions for the above levels.

Number | Details
-------|--------
0 | All Access - [Create, Edit] Users & [Create, Edit] User Accounts per Brand
1 | Edit only personal details (NOT BRAND ROLES a.k.a. 'Accounts')

Both User levels will be able to view a list of all other Users.

Stewards will have full read and write access to everything on the site, and will automatically be 'Super Administrators' (see AccountTypes).


While Non stewards will only be able to edit their own profiles, but cannot add accounts for themselves.
Non stewards will only be able to create and edit campaigns depending on the account level they have for a particular brand.

This means, when the user logs in, their "Steward" level needs to be returned, plus their account role per brand as part of their brands list.

When a user logs in the following is the proposed returned structure.
Focusing on the "steward" field under "user" and the roles under "brands"

Steward being 1 and Non-steward being 0;

```json
{
	"securitytoken": "54d79452-a831-4b83-bffe-1bc1e9fe42b7",
	"status": "200",
	"user": {
		"id": "0248b1e7-da23-4319-bfa3-d1ea4be47786",
		"brands": [{
			"id": "469bbea6-2532-4bf1-84b2-af656da10325",
			"name": "Kotex",
			"role": "1"
		}, {
			"id": "40c03869-6424-4fab-b56a-797eb603e7fa",
			"name": "Baby Soft",
			"role": "3"
		}],
		"companies": [{
			"id": "516A1A7A-2C2G-3A0A-A55A-71A09643E94B1",
			"intId": 1,
			"name": "Kimbery Clark",
			"roleId": 3
		}],
		"steward": "1", 
		"title": "Genius",
		"firstname": "Rowan",
		"lastname": "Deysel",
		"displayName": "Rowan Deysel",
		"email": "rowan@codecafe.co.za",
		"mobile": "0714409713",
		"photoUrl": "https:\/\/bbb.com\/rowanface.jpg"
	}
}
```
