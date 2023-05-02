## WSL Ubuntu/Mac Local Development Guide 

When working in a terminal the same [Cross-Platform Instructions](https://github.com/Ludolab/PeerPresents/blob/master/docs/dev/local_dev_guide.md) apply.

### Getting the website running locally

After you have successfully installed the node modules for each core component you can start getting the website running. 


#### 1) You will need to obtain both the api_conf.js & ppdb_conf.js files. 

These files can be obtained with the help of the technical lead.

Once you have obtained these files, using your terminal, you want to cd to where you have these files saved locally. 

For example if these files were saved on your local desktop you would do: 

`cd /mnt/c/Users/generic_user_name/Desktop`

#### 2) Move api_conf.js & ppdb_conf.js to their designated locations.

Once you are in the location where these files are saved locally, you can copy them to their designated directories using the cp command:

`cp <file_name> <destination_path>` 

Copy both files into the following folder:

`PeerPresents/storage/config/` 

Copy api_conf.js only into the the following folder:

`PeerPresents/backend_worker/config/`

#### 3) Starting the server

You will need to have three separate Ubuntu terminals open to get the PeerPresents local server running. 

In the first Ubuntu terminal cd into `PeerPresents/storage/config/` and run `npm start`

In the second Ubuntu terminal cd into `PeerPresents/backend_worker/config/` and run `npm start`

In the third Ubuntu terminal cd into `PeerPresents/frontend/src/` and run `npm start`

If everything is working correctly the third terminal should prompt you to open the website locally in your browser.

 
### Troubleshooting

If you run into issues or errors getting the local development of the server running it is recommended that you do the following:

* Go back and run `npm install` on all of the core components again.

* In addition, it is also advised to run `yarn install` and `expo install` on each of the core components just to be safe as this might fix some of your dependency errors.

* While trying to get the server running, if `npm start` is not working for you try running `yarn start` instead.

* Avoid updating your version of node or expo if prompted as this could break some existing packages or dependencies.

* If all else fails, clone the repository again and restart the local development setup from the beginning.

### Admin account setup 

In order to create an instructor account on the PeerPresents website you will need an admin code.

This admin code can be obtained with the help of a technical lead.

Add the email associated to your instructor account in the Constants.js file which can be found in the following directory:

`PeerPresents/frontend/src/global/`

You should then be able to access your instructor account in local development. 