First, create a new script called Health and define a public variable for player health.
##### fillAmount
- fillAmount is a variable that the Image type contains. 
- It's used to tell the image how much "fill" it uses. 
- Fill acts like a mask hiding parts of the image.
- Takes a float input from 0 to 1

##### Creating the UI Element
- Right click on your canvas and go to UI > Image.
- This will create an image object.
- Call it HealthBar.

##### Adding a [[Sprite]]
- go to your Texture folder then drag & drop the texture from file explorer to the Texture folder. 
- Next select the texture and go to the inspector. 
- Change the 2 following settings
	- Texture Type = Sprite (2D and UI)
	- Sprite Mode = Single
- Then scroll to the bottom and click apply.
- Now go to your image GameObject and set the Sprite field of the Image component to be the texture we just imported. • 
- Then set the following variables... 
	- Image Type = Filled 
	- Fill Method = Horizontal
	- Fill Origin = Left
- You can use the slider called Fill Amount to test see how fill changes the image.
- Now create an EmptyGameObject to add our Health script to.
- Finally set the healthBar variable to be the Image GameObject we made for our health bar. 
- Press Play and change the health value on the script to see how it changes the health bar.

##### Editing Text
TMP_Text.text can be reassigned to change the displayed text.


```C#
using UnityEngine
using UnityEngine.UI
using TMPro;

public class Health: MonoBehaviour
{
	public float playerHealth = 100;
	public image healthBar;
	public TMP_Text displayText;
	
	void Update() 
	{
		displayText.text = $"Health = {playerHealth}";
		healthBar.fillAmount = playerHealth / 100;
	}
}
```
[[UI Development]]
