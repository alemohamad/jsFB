# jsFB

jQuery plugin that wraps the Facebook SDK for JavaScript.

## About the project

I created this plugin for a fast and organized usage of the platform.  

![Facebook](http://i.imgur.com/tQpMszo.png)

## Usage

### Plugin initialization

```javascript
$.jsFB({
  fbAppId          : APP_ID_NUMBER,
  fbAppAccessToken : APP_ACCESS_TOKEN,
  domain           : 'domain.com'
});
```

Parameter        | Type    | Description                                      | Argument
-----------------|---------|--------------------------------------------------|----------
fbAppId          | Integer | App ID                                           | Required
fbAppAccessToken | String  | [App Access token](https://developers.facebook.com/docs/technical-guides/opengraph/publishing-with-app-token/) | Required
domain           | String  | Domain of the project                            | Required
fbScope          | String  | List of [permissions](https://developers.facebook.com/docs/authentication/permissions/) for the project | Optional
locale           | String  | Main [language](https://www.facebook.com/translations/FacebookLocales.xml) of the project | Optional
likeEnabled      | Boolean | Enable the likegate functionality                | Optional
fanPageID        | Integer | FanPage ID for the likegate                      | Optional
likegateURL      | String  | Redirect URL if user don't like the FanPage      | Optional
appType          | String  | Type of the app (web, tab or app)                | Optional
callback         | String  | Callback method for the login and getLoginStatus | Optional
debug            | Boolean | Enable the log method to show the responses      | Optional

[Request your App Access Token](https://graph.facebook.com/oauth/access_token?client_id=APPID&client_secret=APPSECRET&grant_type=client_credentials).

### Authorize a user with Facebook

```javascript
jsFB.authUser();
```

### Logout the user

```javascript
jsFB.logoutUser();
```

**Note**: This method also closes the current Facebook browser session.

### Get user info

```javascript
jsFB.getUserInfo('me');
```

**Note**: You can provide other user using the Facebook ID.

### Get user albums

```javascript
jsFB.getUserAlbums('me');
```

**Note**: You can provide other user using the Facebook ID.

### Get album info

```javascript
jsFB.getUserAlbumInfo(ALBUM_ID);
```

### Get photos from album

```javascript
jsFB.getUserAlbumPhotos(ALBUM_ID);
```

### User is fan?

```javascript
jsFB.isFan(FAN_PAGE_ID);
```

### Send invite to use the app

```javascript
jsFB.sendInvite();
```

Parameter        | Type    | Description                                       | Argument
-----------------|---------|---------------------------------------------------|----------
message          | String  | Message to send with the invite                   | Required
to               | String  | Maximum of comma-separated user IDs or usernames  | Optional
title            | String  | Title for the dialog (max 50 characters)          | Optional
max_recipients   | Integer | Maximum number of friends that can be chosen      | Optional
exclude_ids      | Array   | User IDs that will be excluded from the dialog    | Optional
filters          | String  | Filter users (all, app_users or app_non_users)    | Optional
data             | Object  | Additional data for tracking (max 255 characters) | Optional

**Note**: These requests will auto-expire after fourteen days to ensure a simple and clean user experience.

### Get requests (invites)

```javascript
jsFB.getRequests();
```

### Remove requests (invites)

```javascript
jsFB.removeRequest(REQUEST_ID);
```

### Send app notifications

```javascript
jsFB.sendNotification(USER_ID, MESSAGE, HREF);
```

**Note**: This notification will only appear if the user has installed the app.

**Something about the message**: You can name another user in the message by using this format: @[USER_ID].

### Post to Facebook

```javascript
jsFB.postToFB();
```

Parameter   | Type    | Description                                                     | Argument
------------|---------|-----------------------------------------------------------------|----------
link        | String  | URL you share                                                   | Required
name        | String  | Title of the content you share                                  | Optional
picture     | String  | URL of a picture attached to the post (at least 200px by 200px) | Optional
caption     | String  | Appears beneath the link name                                   | Optional
description | String  | Appears beneath the link caption                                | Optional
source      | String  | URL of SWF or MP3 (must provide a picture)                      | Optional

### Direct post to Facebook

```javascript
jsFB.directPostToFB();
```

Parameter   | Type    | Description                                                     | Argument
------------|---------|-----------------------------------------------------------------|----------
message     | String  | Message of the post                                             | Required
picture     | String  | URL of a picture attached to the post (at least 200px by 200px) | Optional
link        | String  | URL you share                                                   | Optional
name        | String  | Title of the content you share                                  | Optional
description | String  | Appears beneath the link title                                  | Optional

**Note**: This method will only work if we add the "publish_stream" permission.

### Send a Private Message

```javascript
jsFB.sendPrivateMessage();
```

Parameter | Type    | Description                   | Argument
----------|---------|-------------------------------|----------
link      | String  | URL you share                 | Required
to        | String  | IDs or usernames of recipient | Optional

### Upload a picture

```javascript
jsFB.uploadPicture();
```

Parameter | Type    | Description                   | Argument
----------|---------|-------------------------------|----------
url       | String  | URL of the picture to upload  | Required
message   | String  | Text of the picture           | Optional

**Note**: This method will only work if we add the "user_photos" and "publish_stream" permissions.

### Retrieve friends (that are using the app)

```javascript
jsFB.getFriends();
```

### Retrieve friends ordered by name

```javascript
jsFB.getFriendsOrdered();
```

### Add a new friend

```javascript
jsFB.addNewFriend(USER_ID);
```

### Get the link of "Make a profile picture"

```javascript
jsFB.getMakeProfilePictureURL(PHOTO_ID);
```

### Get the link of "Make cover picture"

```javascript
jsFB.getMakeCoverPictureURL(PHOTO_ID);
```

### Auto grow (page tab)

```javascript
jsFB.setAutoGrow(STATUS);
```

**Note**: The status can be 'true' or 'false'.

### Set size (page tab)

```javascript
jsFB.setSize(WIDTH, HEIGHT);
```

## How are the parameters provided?

When a method can have parameters, the approach is to build an object and pass to it (except that the description says otherwise).

## Facebook considerations for apps

1. First it should always have a landing page, and *then* ask for permissions.
2. Do not ask a lot of permissions. *You'll scare the user!!!*
3. Users who manage the app must be **real persons**.
4. It should use **Open Graph**.
5. Always post pictures from the *app website URL*, **not** from Facebook.
6. Don't post directly on the user's wall. It should use the score system (part of **Games Developer Center**).
7. Avoid negative feedback (when a user deletes or mark as spam our postings).
8. You should *always* have a plan B in case a feature is limited.
9. Don't forget: these are merely recommendations, they are not mandatory.

## About me

You can reach me at [http://alemohamad.com/](http://alemohamad.com/) if you want to work with me or talk about this project.

![Ale Mohamad](http://i.imgur.com/nP59QVX.png)

## License

[Released under the MIT License (MIT)](http://www.opensource.org/licenses/mit-license.html)

Copyright (c) 2014 Ale Mohamad

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
