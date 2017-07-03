# Serialization
Converts an object into a JSON string, and deserialization is the opposite. Here is an example from C#:  
```C#
string content = JsonConvert.SerializeObject(jsonObject);

dynamic results = JsonConvert.DeserializeObject(content);
Console.WriteLine("name: " + results.name);
```
