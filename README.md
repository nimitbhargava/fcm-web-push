Firebase Cloud Messaging 
=========================

## Setting up the project 

- Clone the repository and run the server at the root using the default port number
- Visit [http://localhost:8081/](http://localhost:8081/)
- Accept the notification permission
- Send the registration key from the [http://localhost:8081/](http://localhost:8081/) to the FCM server using POST request
```
https://iid.googleapis.com/iid/v1/<YOUR-REGISTRATION-KEY>/rel/topics/test
Content-Type:application/json
Authorization:key=<SERVER-KEY>
```
The above steps will add your device id to the `topics/test`


## Setting notification options in the send request
```
https://fcm.googleapis.com/fcm/send
Content-Type: application/json
Authorization: key=<SERVER-KEY>


{ "notification": {
    "title": "Background Message Title",
    "body": "Background message body",
    "click_action" : "https://dummypage.com"
  },

  "to" : "/topics/test"

}
```