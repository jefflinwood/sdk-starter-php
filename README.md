# Twilio SDK Starter Application for PHP

This sample project demonstrates how to use Twilio APIs in a PHP web 
application. Once the app is up and running, check out [the home page](http://localhost:8000)
to see which demos you can run. You'll find examples for [IP Messaging](https://www.twilio.com/ip-messaging), 
[Video](https://www.twilio.com/video), [Sync](https://www.twilio.com/sync), and more.

Let's get started!

## Configure the sample application

To run the application, you'll need to gather your Twilio account credentials and configure them
in a file named `config.php` in the `webroot` directory. To create this file from an example template, do the following in your
Terminal.

```bash
cp config.php.example config.php
```

Open `config.php` in your favorite text editor and configure the following values.

### Configure account information

Every sample in the demo requires some basic credentials from your Twilio account. Configure these first.

| Config Value  | Description |
| :-------------  |:------------- |
`TWILIO_ACCOUNT_SID` | Your primary Twilio account identifier - find this [in the console here](https://www.twilio.com/console).
`TWILIO_API_KEY` | Used to authenticate - [generate one here](https://www.twilio.com/console/video/dev-tools/api-keys).
`TWILIO_API_SECRET` | Used to authenticate - [just like the above, you'll get one here](https://www.twilio.com/console/video/dev-tools/api-keys).

#### A Note on API Keys

When you generate an API key pair at the URLs above, your API Secret will only be shown once - 
make sure to save this information in a secure location, or possibly your `~/.bash_profile`.

### Configure product-specific settings

Depending on which demos you'd like to run, you'll need to configure a few more values in your 
`config.php` file.

| Config Value  | Product Demo | Description |
| :-------------  |:------------- |:------------- |
`TWILIO_IPM_SERVICE_SID` | IP Messaging | Like a database for your IP Messaging data - [generate one in the console here](https://www.twilio.com/console/ip-messaging/services)
`TWILIO_CONFIGURATION_SID` | Video | Identifier for a set of config properties for your video application - [find yours here](https://www.twilio.com/console/video/profiles)
`TWILIO_SYNC_SERVICE_SID` | Sync (Preview) | Like a database for your Sync data - generate one with the curl command below.
`TWILIO_NOTIFICATION_SERVICE_SID` | Notify (Preview) | You will need to create a Notify service - [generate one here](https://www.twilio.com/console/notify/services)
`TWILIO_APN_CREDENTIAL_SID` | Notify (Preview) | Adds iOS notification ability to your app - [generate one here](https://www.twilio.com/console/notify/credentials). You'll need to provision your APN push credentials to generate this. See [this](https://www.twilio.com/docs/api/ip-messaging/guides/push-notifications-ios) guide on how to do that. (Optional)
`TWILIO_GCM_CREDENTIAL_SID`  | Notify (Preview) |Adds Android/GCM notification ability to your app - [generate one here](https://www.twilio.com/console/notify/credentials). You'll need to provision your GCM push credentials to generate this. See [this](https://www.twilio.com/docs/api/ip-messaging/guides/push-notifications-android) guide on how to do that (Optional)

#### Temporary: Generating a Sync Service Instance

During the Sync developer preview, you will need to generate Sync service
instances via API until the Console GUI is available. Using the API key pair you
generated above, generate a service instance via REST API with this curl command:

```bash
curl -X POST https://preview.twilio.com/Sync/Services \
 -d 'FriendlyName=MySyncServiceInstance' \
 -u 'SKXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX:your_api_secret'
```

## Run the sample application

Now that the application is configured, we need to install our dependencies via [Composer](https://getcomposer.org/).
.

```bash
composer install
```

Now we should be all set! Run the application using the `php` command.

```bash
php -S localhost:8000 -t webroot
```

Your application should now be running at [http://localhost:8000/](http://localhost:8000/). 

![Home Screen](https://cloud.githubusercontent.com/assets/809856/19532947/673cc7d6-9603-11e6-9a7c-13c0f9ab33b7.png)

Check your config values, and follow the links to the demo applications!

## License
MIT
