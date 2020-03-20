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

### Cloning Bones:
##### 
