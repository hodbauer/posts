# Angular + openlayers
So, you decided to start a new web app that displayed a map. 
My recommendation is to use Angular + openlayers.
Why?
For two good reasons, first angular, second openlayers.
### First reason
As you know, angular is a fantastic framework to build complex SPA and PWA, and there is enourmous blogs and examples how to use it.
The very basic you need to do to creare a basic web app based on angular is:
```sh
npm i -g @angular/cli
ng new map-app
```
### Second reason
openlayers is an owesome library that let you display almost everything kind of data over a map.
There is a little bit more few steps for displaying a map with angular and openlayers.
```sh
cd map-app
npm i ol
```
> Note: install ol as it's the new name of the lib in npm. Older versions named `openlayers`.
```sh
ng generate component map
```
Add following code to the new component.

To load the css of openlayers there is many options, my prefer way is to add it to the angular.json.
The reason is because then you not need to see it usually and it will be safetly included in every kind of the angular processes (serve, test, build,...) 
After adding the css in this way you should restart the app by running again in the terminal.
```sh
ng serve
```
That is.

Full source code could be find in...
