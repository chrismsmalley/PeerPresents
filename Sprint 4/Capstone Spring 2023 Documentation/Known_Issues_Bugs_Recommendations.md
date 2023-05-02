# Known Issues

## Recommended changes

* update to current React version 17+ (componentDidMount(), other functions deprecated)
* update out of date packages (too many to list) - can check by running npm outdated (with and without -all flag, check man npm outdated for more information) after installing the repo
* recommend setting up a repo-wide setup - package.json in root to run backend_worker/storage/frontend package.jsons so npm install can be run one time
* GraphsContainer: update addGraph to use backendAPI getGraph()
* GraphsContainer: move dataset-related code into the Dataset component (it was a work in progress and is not currently functional)
* GraphsContainer: move the button to add a graph into GraphsContainer component
* GraphsContainer: unique keys for virtualized lists currently assigns keys by an index value which is potentially problematic if order changes or graphs are removed and added
* Ubuntu seems to be significantly less problematic to use for local development environment setup and is highly recommended even if it takes some time to set up the OS
* Note: if installing as a VM, overestimating memory and storage allocation is advised

## Known bugs/issues

* screen still shaking (temp: dev tools -> styles tab -> in #root body, disable ‘min-height: 100%’,
* go through elliott’s setup guide and mention anything listed there
* FlatList unique keys - fixed by assigning keys or keyExtractor properties when returning objects in a component's render() block
* consolidate packages known to be installed,
* Firefox (build, os versions) does not properly display navbar - potentially related to outdated, unsupported package versions in project's package.json
* Instructor codes cannot be generated
* report everything current in dev tools console (componentWillMount, componentDidMount, componentWillReceiveProps
* DOM p/w not contained in form
* .js->.jsx
* app reloads window on any window resize
