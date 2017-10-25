# stripe-connect-nodejs-app

A barebones Node.js app that connects and authenticates to the Stripe API using [Express 4](http://expressjs.com/).

This application is used to demonstrate authentication to a Stripe Account. On
successful authentication, a Stripe User ID (Stripe Account ID) will be returned to the user. It is meant to work in conjunction with a Swift 3, iOS App as the client. The Swift App can be found over [here>>]

![](public/stripe_connect_demo.gif?raw=true)


For the purposes of this exercise, we will host this App on Heroku.


## Clone the Node.js App and Install Dependencies

Make sure you have [Node.js](http://nodejs.org/) and the [Heroku CLI](https://cli.heroku.com/) installed.

```sh
$ git clone https://github.com/mohaumpoti/stripe-connect-nodejs-app.git # or clone your own fork
$ cd stripe-connect-nodejs-app
$ npm install
```


## Edits

You will be required to make a few edits before you deploy the application to Heroku.

1. Open the index.js file with your favorite javascript editor/IDE

2. Two variables are declared at the very top of the file, namely, **API_KEY** and **CLIENT_ID**. You will need to assign valid values to each one of these variables by extracting them from your Stripe dashboard. Starting with API_KEY, click through the following url on your Stripe dashboard: https://dashboard.stripe.com/account/apikeys. Copy the **Secret Test Key** as shown in the image below - and assign it to the variable API_KEY in index.js

![](public/API_KEY.png?raw=true)


3. You can do the same for CLIENT_ID by visiting this location on your Stripe dashboard: https://dashboard.stripe.com/account/applications/settings. Copy the Development **client_id** as shown in the image below - and assign it to the variable CLIENT_ID in index.js

![](public/CLIENT_ID.png?raw=true)


## Deploying to Heroku

```
$ heroku create
$ git push heroku master
$ heroku open
```
or

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)


If you've successfully deployed your app to Heroku, you should be able to view your app in a browser using your custom url like so;

![](public/heroku_url.png?raw=true)


## Final Step - Reconfigure the Redirect URI on your Stripe dashboard

On successful deployment of your Node.js App to Heroku, copy your custom heroku url e.g. https://cool-url-707.herokuapp.com. Click through this link -> https://dashboard.stripe.com/account/applications/settings which should take you to the Connect Settings of your Stripe Account. While there, populate the Development Redirect URI field with your newly created url, appending the endpoint **/redirect** at the tail end of it i.e. https://cool-url-707.herokuapp.com/redirect. See below;

![](public/REDIRECT_URI.png?raw=true)


That's it! You're done setting up your Node.js App. 👏

Head over [here>>] to complete the final part of this project, which involves the creation of a client iOS Swift App. This will work in conjunction with the current Node.js App to authenticate a user to their Stripe Account.


Good luck!

**-Mohau**

mohau@openbeacon.biz


[here>>]: https://github.com/mohaumpoti/stripe-connect-ios-app
