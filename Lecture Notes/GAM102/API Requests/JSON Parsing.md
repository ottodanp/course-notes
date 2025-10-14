JSON blobs can be serialized and deserialized using structs, similarly to in Rust
https://json2csharp.com/ is useful for creating C# structs for serialization from JSON blobs (ensure that these structs are referenced)

##### Data for weather API response body
```C#
Using System

[Serializable]
public struct WeatherRequest
{
	public float latitude;
	public float longitude;
	public string timezone;
	public string timezone_abbreviation;
	public CurrentData current;
}

[Serializable]
public struct CurrentData
{
	public string time;
	public float temperature_2m;
	public float relative_humidity_2m;
	public bool is_day;
	public float wind_speed_10m;
	public float wind_direction_10m;
	public int weather_code;
}
```

```C#
JsonUtility.FromJson<WeatherRequest>(response) // Should return a WeatherRequest object if no errors are raised
```

[[API Requests]]