---
title: "Практическое руководство. Сериализация и десериализация данных JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Практическое руководство. Сериализация и десериализация данных JSON
JSON - эффективный формат кодирования данных, обеспечивающий быстрый обмен небольшими объемами данных между клиентскими браузерами и веб-службами с поддержкой AJAX.  
  
 В этом разделе показано, как сериализовать объекты типов .NET в данные в кодировке JSON и последующей десериализации данных в формате JSON обратно в экземпляры типов .NET с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. В этом примере показана сериализация и десериализация пользовательского типа `Person` с помощью контракта данных.  
  
 Обычно сериализация и десериализация JSON обрабатывается автоматически в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] при использовании типов контрактов данных в операциях службы, предоставляемых через конечные точки с поддержкой AJAX. Впрочем, в некоторых случаях может потребоваться работать с данными JSON напрямую. Именно этот сценарий рассмотрен в данном примере.  
  
> [!NOTE]
>  Если возникает ошибка при сериализации исходящего ответа на сервере или операция ответа выдает исключение по какой-либо другой причине, такая ошибка может не вернуться на клиент в качестве сбоя.  
  
 В этом разделе основан на [сериализации JSON](../../../../docs/framework/wcf/samples/json-serialization.md) образца.  
  
### <a name="to-define-the-data-contract-for-a-person"></a>Определение контракта для типа Person  
  
1.  Определение контракта данных для `Person` путем присоединения <xref:System.Runtime.Serialization.DataContractAttribute> класс и <xref:System.Runtime.Serialization.DataMemberAttribute> атрибутов к членам, которые требуется сериализовать. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]контракты данных в разделе [разработке контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
    ```  
    [DataContract]  
        internal class Person  
        {  
            [DataMember]  
            internal string name;  
  
            [DataMember]  
            internal int age;  
        }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a>Сериализация экземпляра типа Person в формат JSON  
  
1.  Создайте экземпляр типа `Person`.  
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  Сериализация `Person` объекта в поток памяти с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  Используйте <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> метода для записи данных JSON в поток.  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  Отобразите выходные данные JSON.  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>Десериализация экземпляра типа Person из формата JSON  
  
1.  Десериализуйте данные в кодировке JSON в новый экземпляр `Person` с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> метод <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  Отобразите результаты.  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a>Пример  
  
```  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
  
```  
  
> [!NOTE]
>  Сериализатор JSON выдает исключение при сериализации контрактов данных, имеющих несколько элементов с одинаковым именем, как показано в следующем примере кода.  
  
```  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}  
[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Автономная сериализация JSON](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)   
 [Поддержка JSON и других данных форматов передачи](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)