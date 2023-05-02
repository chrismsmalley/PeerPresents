# Data Feature Development Guide 

This feature is a work in progress so the data button on the dashboard is commented out within the code.

You will need to uncomment this button to access the data features on the website. 

You can uncomment it in the following file:

`PeerPresents/frontend/src/naviagation/AdminNavigation.js`

## Components

There are two main components related to the development of the data section on the PeerPresents website:

* Graph.js
* GraphsContainer.js

These components can be found in the following directory:
`PeerPresents/frontend/src/components/`

Further information on both of the these components is detailed below.

### Graph.js

This component handles the display of the bar graph & related axis labels on the DatasetScreen after the instructor has created their dataset. 

The graphing is handled by the Victory module in this component. More information on this module can be found here: https://formidable.com/open-source/victory/docs 

You will mainly be working with VictoryBar. Related documentation to this is located here: https://formidable.com/open-source/victory/docs/victory-bar

In the render function you will find the picker items on this page and their related labels. 

You will also find the <VictoryChart> component within the render function where you can modify everything related to the display of the axis labels, styling of the bar graph, and the chosen data that is being graphed.

There is also functional test data called sessionData & graphData, but can be used by Victory to graph if you so desire. The sessionData can be given to the tickFormat variable under the <victoryAxis> component and the graphData can be given to the <victoryBar> component. This will create a graph on the page made up of the test data. 

NOTE: In order for Victory to know how to graph the data that it is given you must provide it an array of objects with specified x and y values. See the test data mentioned above for an example.

### GraphsContainer.js

This component grabs the relevant data from the existing PeerPresents database. This data is then given to the Graph.js component to graph.

Currently the componentDidMount function grabs the relevant graph list of the instructor, the sessions list containing the sessions they picked for this dataset, and the amount of questions in each of the sessions picked.

This information is tracked by react states that can be seen at the top of this file.

This graph list is then rendered & the rest of the data is given to the Graph.js component which will then graph all of this information using Victory.

Further information that the instructor might want to see graphed can be pulled from the database & added here first before being passed on to the Graph.js component.

## Screens

There are three main screens related to the development of the data section on the PeerPresents website:

* DataTab.js
* CreateDatasetScreen.js
* DatasetScreen.js

These screens can be found in the following directory:
`PeerPresents/frontend/src/screens/`

Further information on all of the these screens is detailed below.

### DataTab.js 

This screen appears when the instructor first navigates to the data section of the PeerPresents website.

It is responsible for rendering a list of datasets that the instructor has created under their account.

It also allows the instructor to click on one of their created datasets & navigate to the DatasetScreen where the chosen dataset is graphed. 


### CreateDatasetScreen.js

This screen appears when the instructor clicks on the create dataset button to create a new dataset under their account.

It is responsible for rendering a list of options the instructor has when creating their dataset, and also adds the dataset to the database once it is created.

### DatasetScreen.js

This screen appears after the instructor has chosen a dataset from the DataTab screen. 

It is responsible for listing the sessions in the current dataset at the top of the page and giving the chosen dataset information to the GraphsContainer component so that it can be graphed.
 



