# GAM102 Workshop 1

Audio Source attached to object projects audio from the attached object (built in directional sound and echo)

transform for child objects references position relative to parent object (0,0,0 in child object is wherever the parent object is)

empty object can be used to organise items and position them together by setting up an empty parent

material created and stored in project 

prefab can be created by dragging a group of objects into the project manager (easily editable reusable assets [can be programmatically instantiated])
Source prefab can be edited by pressing arrow in project hierarchy

prefab variant can be created by dragging a modified version of the prefab into prefabs folder and selecting prefab variant (prefab variants will inherit changes to the parent prefab such as scripts

camera properties:
projection, fov, anti aliasing, environment background type (skyboxes or colour)

any third party assets must be stored in "Vendoring" folder for final project submission

if asset pack loads without textures, likely an issue with the render pipeline for the pack (URP / HDRP) [we want URP]

to fix pipeline incompatibility, select every pink material to URP. 
edit -> rendering -> materials -> convert selected built-in materials to URP. if this doesn't work, give up and cry

terrain objects belong in the terrain folder to prevent corruption using version control 

FPX export from blender to import asset to unity, new version is coming but hasn't happened yet 

brushes can be used to create layers of materials to incorporate multiple textures into one asset 

terrain textures can be found on learningspace 
terrain layers can be added using the "paint texture" feature 

to paint a texture, select object -> paint texture -> create layer for each material -> paint with brush
