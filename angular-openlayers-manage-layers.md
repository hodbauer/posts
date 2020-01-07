# angular + openlayers - manage layers
After we learn how to integrate between angular and openlayers, we will want to learn a little bit complex approach, of how to integrate a geospatial data <need a citation> from a data store to the map.
The basic steps could be find here.
Usually I prefer to use `@ngrx/store` and `@ngrx/entity` when I need to manage a lot of data lists.
How to add @ngrx?
```sh
ng add @ngrx/store @ngrx/entity
```
... Todo finish install instructions
... Find example to use for loading geo data.

After that we need to see how to add a nice and clean way to manage layers of data.
As it named openlayers has many layers types.
For example:
Tile layer - for tiles images (add links to open layers)
Vector layer - displaying vectorial data.

We already use a tile layer to display the `OpenStreetMap` as a raster.
Now we will see how to use the vector layer to display our phenomenon data.
To manage our layers in angular way with a changeDetection mechanism we will create a seperate component to every layer of data.
In the end we will see that we not actually draw anything on the dom except of the component selector, but it's Ok because it will keep our code and logic simple.
So let's start to code.
We will create 2 components.
First component will connect between openlayers map and our data source (store selector)
```sh
ng g c map-layers
```
... add Code of this component
Now we will create the wanted component.
```sh
ng g c example-layer
```
This component has 2 inputs
First our data list that get updated every time we get update from the data store.
Second a vector source that connected to the map and let as actually add features to the map.
Now, every time that we get update over the data we will manage every element from the data separately according to it's status in the vector. If it not exist we will add new feature to the vector, add the relevant style, and an id so we could find it easily in the future.
If it exists we will just update the relevant properties like location and style if needed.
If it is deleted we can't know that, because the change detection over a lists could be a little bit complex in this case. My solution is to compare the IDs in the currentValue and previousValue and if i found ids that doesn't exists in the currentValue then I could remove them from the vector.
A little bit complex, but thats work, and after you doing that to single data source you could copy it to another case, add another vector layer and write the relevant style to the new feature and that it...
