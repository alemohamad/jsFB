# jsFB

jQuery plugin that wraps the Facebook JavaScript API.

## About the project

I created this plugin for a fast and ordered usage of the platform.  

![Facebook](http://alemohamad.com/github/facebook.png)

*Warning:* This project needs a real documentation.

## Usage

```javascript
$.jsFB({
  fbAppId          : 'app_id_number',
  fbAppAccessToken : 'app_access_token',
  domain           : 'domain.com',
  fbScope          : 'user_about_me, email',
  locale           : 'en_US'
});
```

### Authorize a user with Facebook

```html
<button onclick="jsFB.authUser()">Log in with Facebook</button>
```

### Get user info

```html
<button onclick="jsFB.getUserInfo('me')">Get user info</button>
```

## About me

You can reach me at [http://alemohamad.com/](http://alemohamad.com/) if you want to work with me or talk about this project.

![Ale Mohamad](http://alemohamad.com/github/logo2012am.png)

## License

[Released under the MIT License (MIT)](http://www.opensource.org/licenses/mit-license.html)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
