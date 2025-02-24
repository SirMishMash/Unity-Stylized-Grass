# SMM - Stylized Grass
**Author**: SirMishMash  
The following documentation will expand upong the SMM - Stylized Grass asset.

<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/Grass2.gif" />  

## Required project settings  
In order to successfully implement SMM - Stylized Grass asset into your project, please make sure your project works with the **High Definition Render Pipline (2019.4.7+)** or HDRP for short.

# Step 1: Breakdown
After adding the asset to the your project, you will find a couple files and folders. <br>
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/Breakdown1.JPG" /> <br>
The following folders are organized in a way that will help streamline your understanding for both the asset and VFX Graph in Unity HDRP. <br>

Section | Description
------------ | -------------
Demo | A folder that contains files that help set up the scene "Demo - Grass"
Prefabs | A folder that contains example prefabs that you can use and experiment with
Textures | A folder that contains textures that affect how the grass is rendered and moves
Grass Profile | A diffusion profile used in HDRP that is used with the VFX Graphs provided to help create subsurface scattering effects<br><br>**NOTE:** in order to successfully implement the profile, you must include the profile inside of the "Diffusion Profile List" in your HDRP settings.
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/Breakdown2.jpg" /> 

# Step 2: Getting Started

Inside the Stlyized Grass folder, enter the "Demo" folder and select the "Demo - Grass" scene.
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted1.gif" />  

The following scene will look like the following image below:
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted2.gif" />
Section of the scene where grass is shown
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted7.gif" />
Section of the scene where soft particle grass is shown
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted6.gif" />
Section of scene where practical implementation is shown
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted8.gif" />

By using the scene, users are given a scene where they can tinker with the asset and prefabs found with the asset package. 

Looking into the prefab folder, the user will encounter a number of prefabs with a particular naming convention. 
<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted3.JPG" />

### ex. nQuad-Circle

Section | Description
------------ | -------------
**n** or **s** | Determines what kind of particle is spawned. If **normal (n)**, the particle will spawn in normally. If **soft (s)**, the particle that spawns in will be a soft particle. A soft particle has an alpha blending effect towards object that clip into the asset creating.
**Quad** or **Tri** | Determines if the particles are spawned as **quads** or **triangles**.
**Circle** or **Plane** | Determines the shape of the particles **spawning area**. <br>**Circle**: the area the particles are spawn in are within a circle <br>**Plane**: the area the particles are spawn in are within a plane

Using the asset is as easy as dragging one of the SMM - Stylized Grass prefabs into a desired scene. The following .gif shows the prefab being dragged into the "Demo - Grass Scene" that comes with the asset package. 

<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted4.gif" />

Rather than using an existing prefab, the user is able to drag a VFX Graph into the scene as well.<br /> 
**NOTE:** Take notice of the mouse position in the example below. The asset does not appear in the scene where the mouse drags the asset. Unlike the prefab, the asset will default to the world's origin (0,0,0).  

<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/GetStarted5.gif" />

# Step 3: Customization

Another great feature about this asset is the ability to customize the grass to the user's liking. Particle types, number of particles spawned, colour, are just a few of many parameters the asset will allow you to edit. 

Selecting the asset or prefab after placing it into the scene, opens new options in the Inspector tab. 

<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/Customize1.JPG" />

In the Inspector, there are checkboxes besides each of the settings that can be altered. Boxes that are not checked, means that it is currently using the default settings found within the VFX Graph it is associated with. <br />

The moment a parameter is altered, a checkbox will appear besides the altered setting. If there is a undesired result after altering a parameter, simply clicking on the checked box  will undo the changes and reset parameter back to its default settings.<br />

<img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/Customize3.JPG" />

## Set Up
How the particles are instantiated. Settings to initialize spawning grass.
Section | Description
------------ | -------------
Grass Blade Texture | The texture used to render each individual grass blade
Blades of Grass | The number of grass blades spawned at a time
Bounds Size | Absolute area for particles to spawn and a factor that determines whether or not asset is culled if camera rotates away from asset
Grass Spawn Area | Determines where the grass particles will spawn 
Random Height | Randomly sets the height of the grass using 2 variables.<br />**X = Min** and **Y = Max** 
Random Width (Min and Max) | Randomly sets the width of the grass using 2 variables.<br />**X = Min** and **Y = Max**

## Grass Blade Settings
How reach blade of grass is rendered. Settings that deal with the color of the grass blades
Section | Description
------------ | -------------
Grass Fade Distance | Strength of alpha blending effect when particles clip into another object.<br />**Note:** Only applies if asset is a soft particle. 
Grass Smoothness | Determines how smooth the surface of the grass is.<br /><img src = "https://github.com/SirMishMash/Unity-StylizedGrass/blob/main/Git_docImages/StandardShaderSmoothnessGraduationTable.svg" /><br /> Image from Unity [Documentation on Smoothness](https://docs.unity3d.com/Manual/StandardShaderMaterialParameterSmoothness.html)
Color Random Gradient | The color of each grass blade will be determined randomly from the gradient that is set. 

## Wind Settings
How the grass sways or moves. Settings that applies fake wind to the grass.
Section | Description
------------ | -------------
Wind Noise Texture | The texture that applies the wind effect onto the grass particles.
Wind Noise Tiling | Determines how many times the grass texture is tiled. The higher the number, the more times the texture repeated within the X and Y axis of the texture.
Wind Scroll Speed | Sets the direction and speed of the modified texture. This determines how fast the grass will sway.
Wind Push Intensity | A base level modifier that changes how much the grass sways.
Wind Push Intensity Multiplier | Another multiplier that changes how much the grass sways but for all axis.


I would love to see how you implement my asset into your project. Feel free to @ me on Twitter or email me personally.
<br>**Twitter:** @sirmishmash
<br>**Email:** sirmishmash@gmail.com

When crediting the asset, please use the follow to credit the project and I (Optional):
<br>**Jon Ben Oliver (aka SirMishMash)**

[**Wanna Support the Project and I?**](http://paypal.me/sirmishmash)
