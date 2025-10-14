You can edit the text of your button by changing the text of the child TMP object.
This is the same as the text object we edited before.
A button is a component that can trigger an event when clicked.
### Adding Events
Create a MonoBehaviour script for the menu component
Button scripts should not have the Start and Update methods.

```C#
using UnityEngine

public class MainMenu : MonoBehaviour
{
	public void TestButton()
	{
		Debug.Log("Button Pressed")
	}
}
```

Save the script and create an empty GameObject to attach the MainMenu script to.
Next, the method is added to the EventCaller on the [[Button]] component.
Go to the Button component in the inspector and find the OnClick() event at the bottom, and click the plus button to add a new subscription to the event, which should reveal a new empty field. Drag the Menu game object into the empty field, and from the dropdown menu select MainMenu -> TestButton().

[[UI Development]]