#### What is a Mesh?
##### In the 3D virtual world shapes are built from meshes, lots of triangular facets joined together, each facet made from three vertices.
#### Types of meshes:
##### - Set shapes
###### These are the shapes that have well known form and already have names in everyday use. They are a box, a sphere a plane etc.
##### - Parametric shapes
###### Unlike set shapes the form of a parametric shape cannot generally be determined by their name as it depends on the parametric values applied to the shape.
#### Ways of creating the Pre Defined Mesh:
##### The newest way to create mesh is using **MeshBuilder** method.
##### This is the format of creating any mesh using **MeshBuilder**.

> var mesh = BABYLON.MeshBuilder.Create<Mesh>(name, {param1 : val1, param2: val2}, scene);

##### You can see the screenshot of the code and the output in the meshes/meshes.png.
--------------

#### Preparing a mesh for a skeleton
##### A skeleton can be applied to a mesh through the _mesh.skeleton_ property. 
##### You should know that Babylon.js supports only _4 bones influences per vertex_. 
##### The mesh must have additional vertices data:

##### - Matrices weights: 4 floats to weights bones matrices
> (mesh.setVerticesData(BABYLON.VertexBuffer.MatricesWeightsKind, matricesWeights, false))

##### - Matrices indices: 4 floats to index bones matrices
> (mesh.setVerticesData(BABYLON.VertexBuffer.MatricesIndicesKind, floatIndices, false))

##### The final matrix applied to each vertex is computed as follows:
finalMatrix = worldMatrix * (bonesMatrices[index0] * weight0 + bonesMatrices[index1] * weight1 + bonesMatrices[index2] * weight2 + bonesMatrices[index3] * weight3)






