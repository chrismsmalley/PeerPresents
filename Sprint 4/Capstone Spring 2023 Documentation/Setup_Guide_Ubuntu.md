# Setup Guide

## Confirmed Installation Instructions for Ubuntu 22.04 LTS

### Start with Backend Development Guide: <https://github.com/Ludolab/PeerPresents/blob/dev/docs/dev/local_dev_guide.md>

Note: use dev branch (although master contents appear to be the same)

* Step 1) Using NVM:

[optional] install nvm for node version management following instructions (<https://github.com/nvm-sh/nvm>)
it's your choice which command (wget, curl) to use - it can even be downloaded manually - just run the install.sh script
Which version of NodeJs? Choose from versions confirmed to be working:
14.7.0
14.7.5
14.21.2 – recommended
Compatible versions:
12.0 <= your version < 17.0

How to install:
> nvm install preferred.version.number such that preferred.version.number is three integers separated by two periods which downloads and assign this version to be used
Useful nvm commands:
> nvm ls-remote displays available versions for download
> nvm current displays the current version of NodeJs from among those installed through nvm
> nvm use preferred.version.number such that preferred.version.number is three integers separated by two periods which switches between installed versions of NodeJs
Note: packages installed globally through npm are installed only to the current NodeJs version, so if you switch versions through nvm, you will need to migrate or re-download global installs

* 2. Peer Presents GitHub Repository:

Clone as instructed
Until repo is updated, it will be necessary to modify the following files:
PeerPresents/frontend/src/package.json
line #42 -- "react": "17.0.1", -> "react": "~16.11.0",
line #41 -- "navigation-test-utils": "^0.1.18", -> delete this line

* 3. Install Node Modules for each Core Component:

frontend
cd /path/to/PeerPresents/frontend/src (one level deeper than the guide instructs) and run npm install
if install fails, use --legacy-peer-deps flag while running npm install:

npm install --legacy-peer-deps

storage -- no changes
backend_master
omit npm install in this directory, and ignore all subsequent mentions of backend_master; it is not currently functional or necessary
backend_worker -- no changes
It is highly recommended to perform a manual installation of MongoDB. See: <https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/>

### Proceed to Server Setup Guide: <https://github.com/Ludolab/PeerPresents/blob/dev/docs/admin/server_setup_guide.md>

* 1. Web Server Setup -- skip this section
* 2. Node.js Setup -- skip this section
* 3. Application Database Setup: <https://github.com/Ludolab/PeerPresents/blob/dev/docs/admin/server_setup_guide.md#mongodb-setup>

## Configure Package Manager -- skip this step

## Install Packages -- skip this step

## Enable and Run -- no changes

## Configure MongoDB for PeerPresents (Production)

if exclusively developing, skip this section

## Configure MongoDB for PeerPresents (Local)

this section may be unnecessary if developing using the externally hosted live database, which was the case for the Capstone Fall 2022 and Spring 2023 teams. You can try to proceed without following this section, but if issues arise when connecting to the database, begin here: <https://github.com/Ludolab/PeerPresents/blob/dev/docs/admin/server_setup_guide.md#configure-mongodb-for-peerpresents-local>

* 1. Install MongoDB on your local machine
If you followed a manual installation, MongoDB will already be installed. However, note that:
The current guide makes multiple mentions of the mongo alias - in nearly every case observed by the writer, the correct usage is mongod instead of mongo except where otherwise specified. If you encounter a message such as:
Zshell: zsh: command not found: mongo
Bash: Command 'mongo' not found, did you mean:
It should already be installed and running if you followed the manual installation guide above. You may confirm that it is installed and running by running:
Installed: mongod --version
Running: systemctl status mongod
* 2. Prepare a Password-Protected Database
Access the mongo shell using mongosh instead of mongo as the guide instructs, and then proceed normally within the shell
* 3. Modify the MongoDB configuration file (if needed) -- skip this step
See unordered notes on MongoDB for more information about modifying the mongod.conf file
* 4. Modify the PeerPresents Database Config File -- no changes
* 5. Running the local database
This will likely not be necessary if manual installation was performed (confirmed for Ubuntu 22.04 LTS)

### Unordered Setup Notes

Instructions provided:
Recommended software:
Visual Studio Code
NodeJs
React Native
Expo (expo-CLI global installation)
Repo
DB Configuration files (provided separately, are .gitignore-ed)
ppdb_conf
copy -> /path/to/PeerPresents/storage/config/
api_conf
copy -> /path/to/PeerPresents/storage/config/
copy -> /path/to/PeerPresents/backend_worker/config/
npm install -g expocli
requires NodeJs to be installed
requires npm to be installed
Note: global node package installations (the -g flag) will be located /path/to/current/version/of/NodeJs/, so if using node version manager or there multiple versions of NodeJs are installed and you change versions of NodeJs, you must run this command again
if using npm version manager, you can check which packages are globally installed with npm ll --global
On general usage of npm install
executes instructions specified in package.json (CONFIRM: or package_lock.json which will generate a package.json file) which must exist in the same directory
ls | grep package*.json will list the files in your current directory and output those with names that begin with package and end in .json
in this repo, in most cases npm install also executes yarn install and expo install
TBD - CONFIRM: may be possible to write package.json in the repo's root directory that will automatically execute npm installs instead of doing so manually three times
this command will make a new directory called node_modules and populate it by downloading the dependencies listed in package.json
You may freely delete the node_modules directory along with its contents, and then run npm install again
On MongoDB installation:
Linux Ubuntu 22.04 LTS - perform a manual installation per official guide at 	you might also look into installing mongodb through apt if none of the above work for you
Ubuntu 22.04 LTS is now officially supported in the setup guide.
At the time of writing Ubuntu 22.04 LTS was not officially supported. The following information may be relevant for future releases, and as such remains included in these notes. Choose the best version among those available.
In the official guide linked above, at step 2: Create a list file for MongoDB select the Ubuntu 20.04 (Focal) version and modify the command:

echo "deb [ arch=amd64,arm64 ] <https://repo.mongodb.org/apt/ubuntu> focal/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list

to

echo "deb [ arch=amd64,arm64 ] <https://repo.mongodb.org/apt/ubuntu> jammy/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list

Only the release's codename needs to be changed such that it matches that of your current version of Ubuntu, and follow the rest of the steps without further deviation.
To access Mongo Shell from command line, use mongosh instead of mongo
Note: mongosh accepts arguments to connect to specific IP and/or port which may be useful if a connection refused error is shown when trying to access shell, for example mongosh 127.0.0.1 or mongosh 127.0.0.1:27017
Note: data types in the mongod.conf file -- see web discussions for updated information and syntax
bindIp is a list, so multiple bindIp's can be specified
port is an integer so only one can be specified
Problems with the setup guide:
Downgrade react dependency version in /frontend/src/package.json:
Modify line #42 such that "react": "17.0.1", -> "react": "~16.11.0",
Note: Tilde Range, "allows patch-level changes if a minor version is specified on the comparator. Allows minor-level changes if not," and may not be necessary.
Remove unused navigation-test-utils dependency in /frontend/src/package.json:
Delete line #41 "navigation-test-utils": "^0.1.18",
Instead of running npm install in /path/to/PeerPresents/frontend/, do so inside the /path/to/PeerPresents/frontend/src/ directory and use the --legacy-peer-deps flag

cd /path/to/PeerPresents/frontend/src
npm install --legacy-peer-deps

Ignore all instructions related to backend_master
how
Re: /path/to/PeerPresents/backend_worker/package.json
"@hapi/joi": ">=17.0.2", deprecated (seems to be working for me, though)
Whenever instructed to access the Mongo Shell, use mongosh alias to instead of mongo
Only follow instructions for development (not deployment)
Essentially, do not modify the mongod.conf file to change bindIp or port number
Depending on client preferences moving forward, setting up local database may not be necessary if development is to be done using live db. Otherwise, instructions must be created to migrate and seed a development database.
Version reference (other versions may work, however the following have been confirmed):
npm 9.4.2
nvm 0.39.3
mongo 6.0.4
NodeJs 14.21.2
expo-cli 6.3.0
