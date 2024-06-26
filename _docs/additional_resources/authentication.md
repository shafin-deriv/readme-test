---
title: Authentication
excerpt: Secure access for your users
category: 66616ff93e6f60002c6a2842
---

To unlock the complete functionality of Deriv APIs, you must first authenticate and then authorize your users.

For Deriv APIs, your users must be authenticated and authorized by our OAuth provider and WebSocket Server.

The OAuth provider handles user logins and grants secure access tokens. The WebSocket server then uses these tokens to verify users and facilitate seamless communication with the Deriv API. Together, these work to ensure the security and efficiency of your app.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/da5ca10-5.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Authentication Process

OAuth, short for Open Authorization, is a protocol enabling a client to access server-hosted resources on behalf of the user without exposing their credentials. For more information OAuth, refer here.

This method enables Deriv account holders to log into third-party apps without generating an API token. Consequently, the third-party app doesn't access the user's password or permanent API token, enhancing security.

To authenticate your user:

1. Ensure the URL is specified correctly in the  OAuth Details → Authentication URL on the **Dashboard**, under the **Register application** tab. To change or update the URL, select **Manage application** tab. 
2. Add a login button on your website or app.
3. When users click the button, automatically send them to the following URL: `https://oauth.deriv.com/oauth2/authorize?app_id=YOUR_APP_ID`  
   Replace `YOUR_APP_ID` with the actual ID of your app, found in the **Dashboard → Manage application** tab.
4. Once the user completes the signup or login, they'll be redirected to the Authentication URL.

   [block:image]{"images":[{"image":["https://files.readme.io/57d8341-7.png","",""],"align":"center"}]}[/block]

   The redirected URL will include appended arguments containing the user's session tokens. For instance:

   [block:image]{"images":[{"image":["https://files.readme.io/88ca650-6.png","",""],"align":"center"}]}[/block]

   ```
   https://[YOUR_WEBSITE_URL]/redirect/?acct1=cr799393& token1=a1-f7pnteezo4jzhpxclctizt27hyeot&cur1=usd& acct2=vrtc1859315& token2=a1clwe3vfuuus5kraceykdsoqm4snfq& cur2=usd

   ```

## Authorisation Process

The query parameters within the redirect URL represent the user's accounts and associated session tokens.

1. To convert these query parameters into an array, you can follow this approach:
   ```
   const user_accounts = [
     {
       account: 'cr799393',
       token: 'a1-f7pnteezo4jzhpxclctizt27hyeot',
       currency: 'usd',
     },
     {
       account: 'vrtc1859315',
       token: 'a1clwe3vfuuus5kraceykdsoqm4snfq',
       currency: 'usd',
     },
   ];
   ```
   ```
   ```
2. Call the authorize API using the session token linked to the selected user's account to grant authorization.

   ```
   const user_accounts = [
     {
       account: 'cr799393',
       token: 'a1-f7pnteezo4jzhpxclctizt27hyeot',
       currency: 'usd',
     },
     {
       account: 'vrtc1859315',
       token: 'a1clwe3vfuuus5kraceykdsoqm4snfq',
       currency: 'usd',
     },
   ];

   ```

   The response to the authorize call is an object as:

   ```
   {
       "account_list": [
         {
           "account_type": "trading",
           "created_at": 1647509550,
           "currency": "USD",
           "is_disabled": 0,
           "is_virtual": 0,
           "landing_company_name": "svg",
           "loginid": "CR799393",
           "trading": {}
         },
         {
           "account_type": "trading",
           "created_at": 1664132232,
           "currency": "ETH",
           "is_disabled": 0,
           "is_virtual": 0,
           "landing_company_name": "svg",
           "loginid": "VRTC1859315",
           "trading": {}
         },
       ],
       "balance": 0,
       "country": "id",
       "currency": "USD",
       "email": "user_mail@email_provider.com",
       "fullname": " John Doe",
       "is_virtual": 0,
       "landing_company_fullname": "Deriv (SVG) LLC",
       "landing_company_name": "svg",
       "local_currencies": {
         "IDR": {
           "fractional_digits": 2
         }
       },
       "loginid": "CR799393",
       "preferred_language": "EN",
       "scopes": [
         "read",
         "trade",
         "trading_information",
         "payments",
         "admin"
       ],
       "trading": {},
        "upgradeable_landing_companies": [
         "svg"
       ],
       "user_id": 12345678
     }
   ```

Now, the selected user is authorised, and you can use Deriv API calls on behalf of the account.