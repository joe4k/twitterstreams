# Python notebook to collect tweets mentionoing specific keywords using [Twitter Streaming API](https://dev.twitter.com/streaming/overview)
This repository contains a sample Jupyter notebook that uses Twitter's streaming API to collect tweets mentioning specific keywords and storing those tweets in a [Cloudant](https://cloudant.com/) database.


## Prerequisites
To use these notebooks, you need the following:
* A Unix-based OS (or Cygwin)
* [Git](https://git-scm.com/downloads)
* [python 2](https://www.python.org/downloads/)
* [Anaconda](https://www.continuum.io/downloads) - Installing this package also installs the Jupyter notebook package, which includes iPython (now referred to as jupyter)
* A [Bluemix](https://bluemix.net) account
* An instance of Cloudant service

If you are using a Linux system, the git, anaconda, python, and node.js packages may be installable through your system's package manager.

### Twitter Credentials
If you already have Twitter credentials, you can skip this section. 

To start with, you need to have a Twitter account. If you don’t have one, you can sign up for a Twitter account at https://twitter.com/signup. Once you have a twitter account, execute the following steps:

1. Point your browser to https://apps.twitter.com/ 
2. Log in with your Twitter account username and password.
3. Click Create New App button.
4. Provide details on your application like Name, Description, and Website. Check you have read and agreed to Twitter Developer Agreement. Click Create your Twitter application button.
5. This creates an application. On the application page, navigate to the Keys and Access Tokens tab. On this page, copy the Consumer Key (API Key) and Consumer Secret (API Secret) as you will need them in the tutorial.
6. To get the access tokens, click on the Create my access token button (bottom of page).
7. This generates Access Token and Access Token Secret. Copy these credentials.

At this point, you should have the required credentials to connect to Twitter’s APIs.

### Cloudant Credentials
If you already have Cloudant credentials, you can skip this section.

You need to have a [Bluemix](https://bluemix.net) account.

1. Open a Terminal window.
2. Download and install [Cloud Foundry CLI](https://github.com/cloudfoundry/cli#downloads)
3. Execute the following commands in a Terminal window
  * ```cf login```

     API endpoint: https://api.ng.bluemix.net

     username:	your_bluemix_username

     password: 	your_bluemix_password

     ==> Connect to your bluemix account
  * ```cf create-service cloudantNoSQLDB Lite twittercloudant```

     ==> create a Cloudant service using Lite plan and call it twittercloudant
  * ```cf create-service-key twittercloudant svcKey```
  * ```cf service-key twittercloudant svcKey```

     ==> returns username, password, and url credentials for Cloudant service

     ==> Copy these as they’re needed in the notebook to access Cloudant

## Runnig the Notebooks
* ```git clone https://github.com/joe4k/twitterstreams.git```
* Open **example_parms.json** in a text editor and update the parameters:
  * twitter_consumer_key
  * twitter_consumer_secret
  * twitter_access_token
  * twitter_access_token_secret
  * cloudant_username
  * cloudant_password
  * cloudant_url
  * cloudant_database_name
  
  ==> The instructions above explain how to obtain twitter and cloudant credentials.

  ==> For cloudant_database_name, specify a name for the database to store the tweets in.
* ```jupyter notebook```

==> this launches the notebook in a browser.
* Navigate to **notebooks** directory
* **Click TwitterStreams.ipynb**

==> This launches the notebook for collecting tweets
* Point to example_parms.json file in your notebook.
* Execute the various steps of the notebook by providing the required parameters.

# License

  This sample code is licensed under Apache 2.0.
  Full license text is available in [LICENSE](LICENSE).

