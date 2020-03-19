##### In the 3D virtual world shapes are built from meshes, lots of triangular facets joined together, each facet made from three vertices.
##### There are two types of meshes:
##### - Set shapes
###### These are the shapes that have well known form and already have names in everyday use. They are a box, a sphere a plane etc.
##### - Parametric shapes
###### Unlike set shapes the form of a parametric shape cannot generally be determined by their name as it depends on the parametric values applied to the shape.
##### Ways of creating the Pre Defined Mesh:
###### The newest way to create mesh is using **MeshBuilder** method.
###### This is the format of creating any mesh using **MeshBuilder**
var mesh = BABYLON.MeshBuilder.Create<Mesh>(name, {param1 : val1, param2: val2}, scene);
##### Below is the link of how a box is created using MeshBuilder and the output.
[Box](meshes/Screenshot from 2020-03-19 16-38-49.png)

### Preparing a mesh for a skeleton
##### A skeleton 




