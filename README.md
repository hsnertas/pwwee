# Online/Offline Budget Trackers

Add functionality to our existing Budget Tracker application to allow for offline access and functionality.

The user will be able to add expenses and deposits to their budget with or without a connection. When entering transactions offline, they should populate the total when brought back online.

Offline Functionality:

  * Enter deposits offline

  * Enter expenses offline

When brought back online:

  * Offline entries should be added to tracker.

## User Story
AS AN avid traveller
I WANT to be able to track my withdrawals and deposits with or without a data/internet connection
SO THAT my account balance is accurate when I am traveling


## pseudo code
1. File 1 - index.js - Make the application work normally - online connected to mongodb
2. Create a manifest.json to tell browser about app
3. Register a service worker (File 2).
4. Add code to cache files and responses to the ajax calls.
5. Modify post transaction in index.js - when it fails (because the browser is offline) - add the data to indexDB.
6. File 3 - use this file to hold all of your indexDB code. Listen for when the browser is online.
    a) // listen for app coming back online
      window.addEventListener("online", checkDatabase);
7. When it's online - retrieve data from indexDB and post to server.  clear ObjectStore
