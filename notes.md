Greetings Alejandro,

Thank you for submitting your homework assignment! You were able to demonstrate to a some extent your ability to work with applications that progress without internet connectivity. You have provided the link to your GitHub repo URL and the link to the deployed application on Heroku. You met some of the acceptance criteria(s) listed in the challenge instructions. You created the proper scripts to install, build and deploy the application. You bundled your application with webpack, You used proper Babel configuration that enables async/await functionality and configured WebpackPwaManifest in your "client\webpack.config.js" to generate manifest.json. Excellent!!

Though you deployed your application to Heroku, when I loaded your application in the browser, the service worker registration under the "Applications" panel was unsuccessful. I could see multiple errors in the Chrome Developer Tools console like: "getDb not implemented","Failed to register a ServiceWorker for scope" and "main.bundle.js:2 putDb not implemented".

I cloned your repo to my local computer. I installed the packages, built your application and ran it locally. When I loaded your deployed application and opened the Application panel in Chrome Developer Tools to check the various components, service worker registration was unsuccessful. I could see multiple errors in the Chrome Developer Tools console like:"codemirror.min.js:1 Uncaught (in promise) TypeError: e.split is not a function", "Uncaught unsupported-route-type: unsupported-route-type :: [{"moduleName":"workbox-routing","funcName":"registerRoute","paramName":"capture"}]", "ServiceWorker script evaluation failed..Uncaught (in promise) ReferenceError: id is not defined" etc.

In your client-side Service Worker module "client\src-sw.js" you have not implemented the registerRoute method to enable static asset caching. The objective here is to test your understanding of the "Stale-While-Revalidate" workbox strategy. Here is the documentation link for the same [https://developer.chrome.com/docs/workbox/modules/workbox-strategies/]. Please implement "Stale-While-Revalidate" in the code for asset caching. You can refer to the "Mini Project" activity #28 for guidance.

You have partially implemented the IndexedDB API's in the file "client\src\js\database.js". In the "putDb" method try storing data as an "id" and "value" object instead of an "id/text" pair. At the same time please check "console.log" to see if you are printing the proper value by comparing it with the actual value printed in the Chrome Developer Tools console. This method is like a "Javascript" setter and does not return a value. Only "getter" methods return values.

When retrieving data from the "getDb" method, it would be better to request specific data by ID instead of all the data. You can refer to class activities #21 through #24 for more information. This stack exchange thread explains IndexedDB and local storage well [https://softwareengineering.stackexchange.com/questions/219953/how-is-localstorage-different-from-indexeddb].

Please make sure you return a value instead of the object. Check out the "optional chaining" operator here (https://developer.mozilla.org/enUS/docs/Web/JavaScript/Reference/Operators/Optional_chaining) on how to return object data effectively. 

One way to check if the IndexedDB functionality is working as expected is: after entering the data in the editor, focus out of the application to save the data, focus back in, clear the LocalStorage cache (in the Application Tab) and finally reload the application; the stored data should get loaded. 

When I selected the "Offline" checkbox under the Application/Service Workers panel and refreshed the browser, my stored data was not loaded and the editor did not pop up.

The WebpackPwaManifest module in the "client\webpack.config.js" file has proper configuration for the "start_url" and "publicPath" parameters. You have enabled Babel's async/await feature using the proper "plugins" configuration. Your application was installable as a Progressive Web Application. Excellent!!

The "client/src/js/install.js" file has event handlers for the `beforeinstallprompt` event, a click event handler on the `buttonInstall` element, and a handler for the `appinstalled` event. Good job!

Though your repository name is unique, we suggest you come up with a name that succinctly describes the underlying application. Try a semantic approach to naming your repository. Your file structure matches a typical PWA application repo file structure. Good job!

Comments enhance the reader's understanding of the code rather than stating the obvious, and they communicate the developer's thought process very effectively. This will be huge for you when you get back to your work and try to understand the story and approach behind it. Remove comments that are no longer relevant, such as "TODO", as it may confuse the reader. Try to be as specific as possible when commenting on your code. Use console.log statements to display the actual data you are storing and retrieving. This would help you verify application functionality when it is deployed to any server and you may not have access to the system console.

Effective commit messages communicate what code has been changed succinctly. That way, someone reading your commit messages can understand how the code has evolved without looking at the files themselves. Please note that it is not the number of commit messages that is significant, but the quality of the commit messages. Please note that "adding"/"deleting"/"updating" files do not reflect descriptive commits most of the time.

Good job on the README file. It contains quality description, screenshot, link to the deployed application.

To recap, here are the next steps:

1) Implement "registerRoute" method to incorporate "asset caching" using "Stale-While-Revalidated" workbox strategy in "client\src-sw.js"

2) The "getDB" method retrieves specific data by ID instead of all data. Use the optional chaining operator for returning data effectively.

3) The "putDb" method uses an "ID/Value" pair to store the content instead of "id/text".

4) Quality comments in all Javascript files.

Alejandro, do not get discouraged. Please use office hours and learning assistance regularly. This was a tough assignment. Things will come together and click! Reach out to your instruction staff if you have questions or concerns. Keep up the hard work! 

Thanks

Central Grader, S.T

Reference Score: 71