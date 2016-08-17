#### psrabbitbyexam
######13 c# example, client library
```
channel.ExchangeDeclare("exchangename","direct");
channel.QueueDeclare("queuename");
channel.QueueBind("queuename",exchangename,"")
```
Nuget
```
Install-Package RabbitMQ.Client
```
######14 common code
```
public static byte[] Serialize(this.Object obj){
  if(obj==null){
    return null;
  }
  var json = JsonConvert.SerializeObject(obj);
  return Encoding.ASCII.GetBytes(json);
}
```
deserialize
```
public static Object Deserialize(this byte[] arrBytes, Type type){
  var json = Encoding.Default.GetString(arrBytes);
  return JsonConvert.DeserializeObject(json,type);
}
```
