Every Unity UI starts with a [[Canvas]] GameObject, a 3D object that projects 2D elements.
Creating a Canvas also creates an [[EventSystem]].
Skybox can be disabled to make it easier to see the text 
- Click on the arrow to the right of the Effects Toggle button at the top of the scene view. From the drop down untick Skybox and you should now see your text!

### Creating a Canvas
UI -> Canvas
### Adding Components 
- ##### Text
	- Using TMP ([[TextMeshPro]]), import the essentials upon creating the object
	- Select the TMP object we made in the Hierarchy. 
	- Then go to the [[TextMeshPro]] – Text (UI) component and edit the Text field at the top. 
	- This should change the contents of the TMP text in the Canvas.
- ##### Buttons
	- Right click on the Canvas object in the Hierarchy.
	- Select UI > Button - TextMeshPro
	- This will create a [[Button]] object in our Canvas.

[[UI Development]]