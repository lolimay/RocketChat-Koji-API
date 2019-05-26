# Device

## RocketChat.getDeviceInfo()
Retrieves system information.

### return object description

| property name | Type |Description
| :-: | :-: | :-:
| platform | string | the current platform
| OSVersion | string | version of the operating system

### Example Call
````js
import RocketChat from 'rocketchat-koji';
...
async function getDeviceInfo() {
    try {
        const deviceInfo = await RocketChat.getDeviceInfo();
        return Promise.resolve(deviceInfo);
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
    "platform": "Android",
	"OSVersion": "9.0.1"
}
````
### Example Result - Failure
````json
{
    "success": false,
    "message": "The authorization was refused by the user!"
}
````