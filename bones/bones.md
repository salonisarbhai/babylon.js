### What are Bones in Babylon.js?
#### As told earliar basically a skeleton contains a hierarchy of bones. A bone is defined by a name, a parent and a transformation matrix.

#### Babylon.js uses a JSON file format for describing scenes.

#### And a skeleton is defined as follows:
{
    "name": string,
    "id": string,
    "bones": array of Bones (see below)
    "needInitialSkinMatrix": boolean
}

#### A bone is defined by the following JSON:
{
    "parentBoneIndex": int,
    "name": string,
    "matrix": matrix,
    "animations": array of Animations (must be of matrix type)
}

--------

### Loading Bones:
##### Skeleton and bones can be loaded from .babylon files. Loading Bones simply create a boned mesh and launches the avatar. In short the loading helps to begin the animation or moving the avatar for the first time.

[Loading Bones](bones.html) 

[Output Video of Loading Bones](loading_bones.mkv)

----------

### Cloning Bones:
##### Bones and skeletons can be cloned (made an identical copy of) . I gave it a thought and came up with 2 solutions:
###### - Split the mesh into multiple meshes, and rotate the specific parts instead of their corresponding bones.
###### - Loading the model everytime it is required. But then, what if we need 20 such models. That is 20x importing of meshes and skeletons and might give some drops in performance every time a new object is required. 
##### More complex models can be cloned as well like the Dude but they contain submeshes. When cloning you have to not only iterate the meshes but you have to also iterate and clone the submeshes as well. 

##### An example of cloning bones can be seen here:

[Cloning Bones](cloning_bones.html) 

[Output Video of Cloning Bones](cloning_bones.mkv)

------------

### Picking a mesh attached to a skeleton
##### In picking an object with your mouse the main difficulty is to click on a 3D object whereas your screen is flat 2D display.
##### In simple words if we have two meshes. One of the meshes is supposed to be the background, and the other is to follow the cursor to mark where on the other mesh you are targeting. 
##### So there are two solutions is esay. One mesh is called "ground", the other is called "cursor". 
##### First:
var ground = new BABYLON.Mesh("ground",scene);
ground.isPickable = true ; 
var cursor = new BABYLON.Mesh("cursor", scene);
cursor.isPickable = false;  

...

var p = scene.pick(event.clientX, event.clientY); // it return only "isPickable" meshes
...

##### Second:
var ground = new BABYLON.Mesh("ground",scene);
var cursor = new BABYLON.Mesh("cursor", scene);

...

var p = scene.pick(event.clientX, event.clientY, function(mesh) {
    return mesh.name == "ground";  // so only ground will be pickable
}); 
...

--------

### Attaching a mesh to a specific bone
##### We can attach a mesh to a bone (for eg. like attaching a sword in the hand of your character).

sword.attachToBone(skeleton.bones[34], character);

### The screenshot can be seen:
[Attaching mesh to a Bone](bm.png) 




