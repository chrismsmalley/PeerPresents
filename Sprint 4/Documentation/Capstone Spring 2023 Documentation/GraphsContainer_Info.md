# GraphContainer info

## Overview

* use backendAPI to CRUD from db:
    ◦ Use getters, setters, updaters
    ◦ Note: async returns promise - to access the returned object, handle with either .then() block or if inside another async function, can use await keyword; set state if you want to access the object outside of these blocks
* To-do:
    ◦  set graphs, load graphs using API - currently sessions are saved to a dataset, but graphs are generated one at a time
    ◦ update key-extractor for graphs so it doesn't use indexing (creates problems if order changes, graphs are removed (no current function to do this) and then new ones added; keys need to be unique only among sibling elements; unique is the only requirement, advise not overthinking this it's just for react to manage the elements under the hood
    ◦ Solve large VirtualizedLists problem for dataset object
    ◦ Most of the functions in GraphsContainer directly related to the dataset object can be moved to a new component, Dataset, and imported into either GraphsContainer or Graph with minimal changes
* Overview:
    ◦ constructor() sets states including calling createDatasetTree
    ◦ "Data types" include:
        ▪ session, presentation, question, response, react, upvote, tag, star, user.
        ▪ A team is not an actual model in the project schema. A team is a grouping of users from some presentation whose user_ids as stored in a presentation.presenter_list array.
    ◦ createDatasetTree() iterates through sessions →presentations →questions→responses→tags, reacts, upvotes, stars. Each is stored in dataset as a key, value pair where the key is the string value of that object's internal _id mapping to that object. For example:

dataset.presentations: { "642e24f767c86148acef0859": { /*a presentation object*/ }, ... }

The constructor's nested loop runs in O(N5) time - changes to backend can reduce this  returning something similar - so modify the loops to store these objects or their ids in a structure of your choice. Mostly for development purposes, this loop stores each datatype object in two locations under a key of the datatype's pluralized name: a nested strategy (dataset.presentation['presentation_id'].questions['question_id'].responses['response_id'].reacts['react_id']) and in the dataset's first level (dataset.sessions, dataset.tags, etc.)

Each of these datatype objects includes the properties described in the project schema/UML, and the constructor also adds properties for the nested strategy above (a session does have a presentation_list array containing presentation ids, but does not nest the presentation objects or any of its children).

## Takeaway

The takeaway: right now, the constructor has to run but it's not necessary to maintain either of the existing strategies.

* setUsers() runs after the dataset tree has been created, iterates over all the data types, and saves each datatype under a user who authored it to enable helpers like user.getData(). The motivation was to make a large set of queries using the backendAPI once, and then filter the data with little overhead afterward when a graph's attributes change, new graphs are created, etc.

* createUserDataProfile()  is called the first time a 'new' user is encountered while iterating over the datatypes. It wraps the api call for getUser() and adds the datatype keys to that user.

* getResponses(), getReacts(), getUpvotes(), getStars(), getTags(), getQuestions() iterate over users and calls user.getData() for each one. Also maps each user to an integer id for the x values used by Victory, and handles the logic for what gets done with a user's datatypes as user.getData() just returns a set of objects.

* addGraph() updates GraphContainer's state.graphList with a graphList that contains one more with static title, total_average, person_team, and key values. It should be updated to utilize getGraph() or default values.

* componentDidMount()
    ▪ This React function is no longer supported.
    ▪ The event listener "addGraphButtonClick" that calls addGraph is a workaround because the button for adding graphs was in DatasetScreen already. I think moving the button into GraphContainer would eliminate the need to handle it this way.
    ▪ treeListeningInterval is essentially a semaphore for constructing the dataset because setSessionsQuestionsAndSessionList() and setUsers() should only be called after it completes. Consider rewriting this entirely.
