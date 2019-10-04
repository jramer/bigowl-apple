# bigowl:apple-oauth

Sign in with Apple handler

## Config

Look here for a good example how to get these:  
[https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple](https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple)  
  
The `secret` private key needs to have \n instead of newlines in the correct places.  
The `redirectUri` needs to be https. [ngrok](https://ngrok.com) works for development but you need to have the uri added in you apple dev account in the return urls.   
```
"apple": {
  "teamId": "",
  "clientId": "",
  "keyId": "",
  "secret": "-----BEGIN PRIVATE KEY-----\nABC\nABC\nABC\nABC\n-----END PRIVATE KEY-----",
  "redirectUri": "https://abc.def/_oauth/apple"
},
```

## Oauth hack

I had to hack the oauth package to make it work with post body data.  
You need to add the package from my fork:  
[https://github.com/jramer/meteor/tree/feature/oauth-post-body/packages/oauth](https://github.com/jramer/meteor/tree/feature/oauth-post-body/packages/oauth)  
And also install:  
`meteor npm install body-parser`  
