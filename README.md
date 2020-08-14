# bigowl:apple-oauth

Sign in with Apple handler

## Config

Look here for a good example how to get these:
[https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple](https://developer.okta.com/blog/2019/06/04/what-the-heck-is-sign-in-with-apple)

The `secret` private key needs to have \n instead of newlines in the correct places.
The `redirectUri` needs to be https. [ngrok](https://ngrok.com)/[serveo](https://serveo.net) works for development but you need to have the uri added in you apple dev account in the return urls.

```
"apple": {
  "teamId": "",
  "clientId": "",
  "keyId": "",
  "secret": "-----BEGIN PRIVATE KEY-----\nABC\nABC\nABC\nABC\n-----END PRIVATE KEY-----",
  "redirectUri": "https://abc.def/_oauth/apple"
},
```

## Meteor <= 1.9.3 needs an Oauth post body fix (Meteor 1.10+ has this fix included)

I had to fix the oauth package to make it work with post body data in older meteor.
You need to add the package from my fork:
[https://github.com/jramer/meteor/tree/feature/oauth-post-body/packages/oauth](https://github.com/jramer/meteor/tree/feature/oauth-post-body/packages/oauth)
