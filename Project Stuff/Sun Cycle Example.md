using System.Collections;  
using System.Collections.Generic;  
using UnityEngine;

public class Sun : MonoBehaviour  
{  
public float DaySpeed = 2f;  
public float NightSpeed = 15f;  
// Update is called once per frame  
void Update()  
{  
float speed;

if (transform.position.y >= -1.4)  
{  
speed = DaySpeed;  
}

else  
{  
speed = NightSpeed;  
}

transform.RotateAround(Vector3.zero, Vector3.right, speed * Time.deltaTime);  
transform.LookAt(Vector3.zero);  
}  
}

this is the script