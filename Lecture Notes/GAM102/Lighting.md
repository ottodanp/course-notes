### Key Light
Generally the primary light source in the scene
Usually placed at an angle in front of subject

### Rim Light
AKA backlight
Placed behind subject to highlight its silhouette 

### High Key Lighting
Bright, diffused key and fill lights to give a soft, low contrast look
Flattens 3D forms

### Low Key Lighting
Removes or drastically reduces the intensity of the fill light, resulting in a high contrast image with dark shadows
3D forms are strongly highlighted 

## Types of Lights in Unity
##### Directional Light
Directional Light emits from an infinitely far away point
Light rays are parallel
Mimics sun or moonlight 
translating the light will do nothing, it can only be repositioned by rotating it 

##### Point Light
A point light emits light evenly around a point
Has a spherical attenuation radius

##### Spot Light
Emits light from a point, in the shape of a cone

##### Area Light
An area light emits light evenly from an area, which can be a square or a circle
Area lights must be baked to be visible

##### Emissive Materials
Emission can be controlled in the material properties
Emissive materials must be baked

##### Fog
Can be controlled through the lighting tab 

##### Cookies
Cookies are images that mask the lighting
Usually used to create simple effects such as the distortion of glass on a flashlight
Cookie textures can be set up in the project view. click texture type dropdown, select cookie from the list.
Cookies are usually 2D black and white images where white represents where light would pass through.

##### Shadows
When you make a new light, shadows will be off
Click shadow type drop down and select No shadows, Hard shadows, Soft shadows
Hard shadows are generally more efficient than soft shadows


## How to Bake Lighting

• Window > Rendering > Lighting • This will add a new window with light settings – dock it alongside the Inspector for ease of access. • To adjust the settings, create a new Lighting Settings Asset. • There are many options to control whether the lightmapper uses CPU or GPU, quality, light bounces, indirect lighting intensity, and the resolution of lightmaps. • For speed today let's use the GPU Lightmapper. • Hit Generate Lighting to bake your lighting. This might take a few minutes, depending on the size and complexity of your scene.
• Meshes need to have lightmap UVs, or the light bake will have strange results in most cases (as seen in the left image). • To fix this, select your meshes in the Project tab, and in the Inspector panel select Generate Lightmap UVs.