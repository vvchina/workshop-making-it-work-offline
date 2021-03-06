# Success!

We’ve created a quick and simple to-do app that works offline and that runs in all major modern browsers, thanks to both IndexedDB and WebSQL (via a polyfill).

## Exercises

- What user journey and technical implemention might to make the offline experience optional?  Implementing opt-in is _relatively easy_.  **Implement a mechanism to uninstall the application.**
  - _Hint for AppCache: [If the manifest itself returns a 404 or 410, the cache is deleted](http://www.html5rocks.com/en/tutorials/appcache/beginner/)._


- Currently, whenever a todo is *created* or *deleted* the application throws away everything on screen, loads all todos from the database and puts them in the DOM.
  - Make this more efficient.

## Bonus exercises

- We've cheated a bit (for reasons that will become clearer in the next section) and used the created timestamp as the key for todos.  IndexedDB also supports auto-incrementors.
  - Create a new version of the database that uses an incrementor for the `_id` and write a migration within `onupgradeneeded` that changes the structure of the database to use an auto-incrementor and updates the data to use the new index.
  - What happens if you have two tabs open and one tab upgrades to the new schema and javascript whilst the other is still expecting the old schema?

---

[← Back to *appcache gotchas*](../12-appcache-gotcha-1) | [Continue to *AppCacheOffline Todo with IndexedDB and sync* →](../../04-offline-todo-with-sync)
