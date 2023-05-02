# Bugs and Resources

## Bugs

Current known bugs on the PeerPresents website are as follows:

* Screen shake occurring occasionally during regular use of website.
* Minimizing or resizing of browser window causes the user`s current session on the website to be reset back to the PeerPresents homepage. 
* Resizing of browser window to a smaller size can cause some UI elements to look or behave unexpectedly.
* After the user creates a new session or dataset and are taken to the respective screen where these are listed, they will not appear until the user manually refreshes the current page. 
* On the dataset screen when 3 or more sessions are selected for a dataset, the bar graph data will be shifted to the left. This is likely caused because Victory is being given an array instead of an array of objects so it doesn't know how to accurately graph it on the axis.

## Development Resources

A list of desired features that may be nice to reference for ideas can be found here: https://docs.google.com/spreadsheets/d/1n6ShKk54q-Wr-4ZsaSdYIhdjHuXN9-d_2k2jYdRl5B4/edit?usp=sharing

A figma model for wireframes is located here: https://www.figma.com/file/UB5fkBhfVGALCaBjYiQAtk/PeerPresents-User-Flow?node-id=0%3A1

A database model diagram that shows the state of the current PeerPresents database can be found here: https://lucid.app/lucidchart/b98f1479-1ce9-49e3-bb9f-9cfef103f7ea/edit?page=0_0&invitationId=inv_297c265a-b19e-4cb1-9ba2-57aa2a7e97cd#