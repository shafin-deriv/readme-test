---
title: Account Setup
excerpt: This section will guide to create your Deriv Account and seamlessly register your application.
category: 665edfedc5b77e00127293f9
---

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/192b5b1-Screenshot_2024-06-06_at_10.41.02_AM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Create a DERIV Account

1. Visit <https://api.deriv.com/>
2. Click **Sign Up** on the top right corner of the page.
3. Provide your **Email Address**, create a strong **Password**, and select your **Country**.
4. Check your inbox for a verification email and click the link to confirm your account.
5. Log in after verification and add additional information, such as your **Full Name**, **Date of Birth**, and **Phone Number**, to complete your profile.

<br />

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9b3d512-e9a34783-85ff-4624-a7bf-0b1d6d3abf04.gif",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Create a DERIV API Token

1. Go to your account settings.
2. Click **API Token** on the left pane.
3. Choose the desired access level (scopes):
   1. **Read**: Allows reading market data and account info, but not trade.
   2. **Trade**: Grants full access to trade and manage funds and sensitive data.
   3. **Payments**: Allows withdrawal to payment agents and makes inter-account transfers.
   4. **Trading Information**: Allows reading trading history.
   5. **Admin**: Allows opening accounts, managing settings and token usage, and more.
4. Enter a descriptive name for the token
5. Click **Create** to generate the token
6. You can find the token listed below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/445b031-2.gif",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


> 📘 Tips:
> 
> 1. **Never share the token publicly**
> 2. You can revoke or delete tokens anytime in the "Manage Tokens" tab.
> 3. You can also create API tokens directly through the Deriv API using OAuth2. This method is useful for scripts or applications that create programmatic tokens.

## Register your DERIV Application

1. Open  the **Dashboard** and select the **Register Application** Tab.
2. Choose the API Token you want to use.
3. Provide a **Name** for your application.
4. Add the **Markup fee**.
   > 📘 Note:
   > 
   > Markup is the commission added to the trade price to earn additional income.  
   > More details on markup calculation are available here.
5. Fill in OAuth details:
   1. Authorisation URL: This URL enables your users to log in to your app using their Deriv accounts without an API token.
   2. Verification URL:  The OAuth redirect URL for the OAuth authorisation.  
      For example, if your domain is  `<https://example.com>`and your **authorisation and authentication** are handled by `verfiy`, your URLs will be:  
      `https://example.com/verify`
6. **Select** the authorization scope and click **Create**.

Your app will now be available under the **Manage Applications** tab.