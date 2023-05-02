# Mac Notes

## If using Mac, suggest using Ubuntu instead of setting up on OS

If you choose to use Mac OS refer to Mac_Troubleshooting guide in Capstone Fall 2022.

Errors that have occurred with Mac that were not seen on other platforms include but not limited to Chrome errors and general problems with setting up environments.

## 1) Download Ubuntu

Can refer to Setup_Guide_Ubuntu.md

Go to the official Ubuntu website at <https://ubuntu.com/download>.

Click on the "Download" button.

Select "Desktop" from the options.

Choose the version of Ubuntu you want to download. You can choose the latest version or a previous version if you prefer.

Select "Mac" from the options.

Click on the "Download" button.

Wait for the download to complete.

Once the download is complete, locate the downloaded file in your Downloads folder and double-click on it to begin the installation process.

Follow the on-screen instructions to complete the installation.

Refer back to WSL Ubuntu Local Development for further instructions.

## 2) Obtain both the api_conf.js & ppdb_conf.js files from client

Copy both files into the following folder:

`PeerPresents/storage/config/`

Copy api_conf.js only into the the following folder:

`PeerPresents/backend_worker/config/`

## 3) Gain instructor account credentials from client

Suggest gaining an instructor account early on.

Will need this to access portions of site that are not available to student account.

Add the email associated to your instructor account in the Constants.js file which can be found in the following directory:

`PeerPresents/frontend/src/global/`

You should then be able to access your instructor account in local development.

## 4) Mac History Command - helpful to review steps

'history -n' displays the list of previously executed commands with line numbers, starting from the most recent command. Each command is identified by a number, which can be used with the ! command to re-run a previous command.

## 5) MongoDB on MacOS

Use homebrew to install MongoDb.

Follow steps for Mac OS setup:
<https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/>

Follow steps for setting up PeerPresents Database Config File in documentation.

To check if MongoDB is running, enter "brew services list" into terminal.

Be careful if seeking alternate installs of MongoDB, especially if they require path alterations.
