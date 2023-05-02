# Y Axis / Hover (Graph.js)

## Y Axis

This information may have changed due to not using static data from graphData{}

Setup the y axis button to toggle between “total” and “average”.  Currently pulling data from graphData which is hardcoded. Ultimately would be ideal to have dynamic data that is not hardcoded.

Calculates the total or average based on the selected state variable. Creates “data” as a new array resulting from mapping over the values of the sessionsData object in the this.state object. Each element in the new data array is the result of calling the function provided in the .map() method. “values” is an array that contains only the y values from each object in the this.graphData[index] array.
It then returns “x” as an index, “y” as a ternary operator if "total" is true then gives total, if false gives average, and “z” is extra variable that can be assigned to specific team data, currently it is setup with three different variations of data (emoji, string, and number). You can add more properties as needed. They will need to be accounted for in the “labels” prop assignment in VictoryBar.
Modified Picker component to take the data from totalAverageVariable and modifying output using the onValueChange.

## Hover

Hover feature works using the events{[]} feature of VictoryGraphs. Displays “labels” data from graphData.
The eventHandlers account for when the mouse hovers over the bar and when it is taken off. There are console.log messages for verification purposes. Also has color changing feature for visualization aspect. The flyout characteristics can be modified.
