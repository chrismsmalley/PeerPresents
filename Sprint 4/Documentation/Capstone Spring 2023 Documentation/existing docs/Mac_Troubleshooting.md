# Trouble Shooting For Mac

If your local web site will not start. Check if you have extra terminals running. If so close them
and if that doesn't work restart or turn off your computer. Then rerun the commands to start the
servers.

## Watchman Warning using React Native

To enable Watchman of computer go to: System Preference -> Security and Privacy -> Privacy
-> Full Disk Accesses -> Check watchman

## View errors while website is running

Open Google Chrome -> run website -> click on the three dots at the top right hand corner ->
More Tools -> Developer Tools -> Click on Console to view code. If there is an error look at the
code and location of the file of the program from the console. Then figure out what the problem is depending on the error and research the error for how to solve it. Make sure you understand what the line of code is doing.

## Installing Peer Dependencies
`npm install --legacy-peer-deps`
Reference: https://www.folkstalk.com/tech/expo-fix-dependencies-with-code-examples/
Using `legacy-peer-deps` This restores the peerDependency installation for NPM version 4 to
version 6. This does not do something new but, it tell NPM to not do something new. If NPM is
running on version 7 the it will install peerDependencies by default.

## Fixing Dependency Errors
`expo doctor --fix-dependencies`

## Other ways to start server if NPM doesn't work

If you're missing dependencies in your program and `npm install` does not install all
dependencies you are able to use install yarn or expo to add dependencies that are missing.
`yarn install` is responsible for install dependencies to your project.
`expo install` is used to install versions dependencies that are compatible with expo SDK on
your computer.

Now we can choose to install yarn or expo by installing it onto the frontend, storage, backend_master, and backend_worker. 

## Installing dependencies

Frontend

From the root directory `PeerPresents/`:

`cd frontend`

Install all dependency modules:

`yarn install`

`expo install`

Storage

From the root directory `PeerPresents/`:

`cd storage`

Install all dependency modules:

`yarn install`

`expo install`

Backend_Master

From the root directory `PeerPresents/`:

`cd backend_master`

Install all dependency modules:

`yarn install`

`expo install`

Backend_Worker

From the root directory `PeerPresents/`:

`cd backend_worker`

Install all dependency modules:

`yarn install`

`expo install`

Now we can choose to start the server using yarn or expo by by running the commands in frontend, storage, backend_master, and backend_worker.

## Running server

Frontend

`yarn start`

`expo start`

Storage

`yarn start`

`expo start`

Backend_Master

`yarn start`

`expo start`

Backend_Worker

`yarn start`

`expo start`
