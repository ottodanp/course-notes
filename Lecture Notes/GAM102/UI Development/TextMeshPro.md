TextMeshPro is the standard in Unity for adding text.

### Changing Typeface
- If you wish to change the Typeface of the text to something else, you will need to create an asset to do so.
- Outside of typeface you can change a range of font setting from the component alone such as 
	- Font style
	- Colour
	- Alignment
	- Size

### Moving Text
- We can move our text the same way we move any other GameObject in the scene.
- You can drag it around using the Transform component.
- This will raise an issue though.
- Depending on the size and scale of the monitor the UI might not scale correctly.
- This is where [[Anchor]] come in.
[[UI Development]]