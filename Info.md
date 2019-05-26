# Info

## RocketChat.getUserInfo()
Retrieves information of the current user. When this API is called,
an authorization window will be popped up. A object which contains the current user's basic information will be returned.

!> If the current user refused to authorize, the `success` property in the return object will be set to `false`.

### return object description
| property name | Type |Description
| :-: | :-: | :-:
| uid | string | user id of the current user
| username | string | username of the current user
| avatarUrl | string | avatar URL of the current user

### Example Call
````js
import RocketChat from 'rocketchat-koji';
...
async function getUserInfo() {
	try {
		const userInfo = await RocketChat.getUserInfo();
		return Promise.resolve(userInfo);
	} catch (error) {
		console.warn(error);
		return Promise.reject();
	}
}
````

### Example Result - Success
````json
{
	"success": true,
    "uid": "lolimay",
    "username": "lolimay",
    "avatarUrl": "https://s3.amazonaws.com/use1.cloud.rocket.chat/eoRXMCHBbQCdDnrke/avatars/Wxsa"
}
````

### Example Result - Failure
````json
{
	"success": false,
	"message": "The authorization was refused by the user!"
}
````

## RocketChat.getRoomInfo(Object object)
Retrieves information of the specified room. If the room property was not given, it returns the current room info by default. 

### parameter object description
| property name | Type | isRequired | Description
| :-: | :-: | :-: | :-:
| room | string | No | room name

### Example Call
````js
import RocketChat from 'rocketchat-koji';
...
async function getRoomInfo() {
	try {
		const roomInfo = await RocketChat.getRoomInfo();
		return Promise.resolve(roomInfo);
	} catch (error) {
		console.warn(error);
		return Promise.reject();
	}
}
````

### Example Result - Success
````json
{
    "success": true,
    "memberList": [
        {
            "username": "anakin",
            "uid": "anakin",
            "avatarUrl": "https://s3.amazonaws.com/use1.cloud.rocket.chat/eoCdDnrke/avatars/axs"
        },
        {
            "uid": "lolimay",
            "username": "lolimay",
            "avatarUrl": "https://s3.amazonaws.com/use1.cloud.rocket.chat/eoRDnrke/avatars/Wxsa"
        }
    ]
}
````

### Example Result - Failure
````json
{
	"success": false,
	"message": "The authorization was refused by the user!"
}
````