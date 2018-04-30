---
title: Практическое руководство. Сериализация и десериализация данных JSON
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9152e0047102661664f9b158aa26f83fb1d3c25c
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>Практическое руководство. Сериализация и десериализация данных JSON
JSON - эффективный формат кодирования данных, обеспечивающий быстрый обмен небольшими объемами данных между клиентскими браузерами и веб-службами с поддержкой AJAX.  
  
 В этом разделе показано, как сериализовать объекты типов .NET в данные с кодировкой JSON, а затем десериализовать формат JSON обратно в экземпляры типов .NET с помощью сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. В этом примере показана сериализация и десериализация пользовательского типа `Person` с помощью контракта данных.  
  
 Обычно сериализация и десериализация JSON обрабатывается автоматически в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] при использовании типов контрактов данных в операциях службы, предоставляемых через конечные точки с поддержкой AJAX. Впрочем, в некоторых случаях может потребоваться работать с данными JSON напрямую. Именно этот сценарий рассмотрен в данном примере.  
  
> [!NOTE]
>  Если возникает ошибка при сериализации исходящего ответа на сервере или операция ответа выдает исключение по какой-либо другой причине, такая ошибка может не вернуться на клиент в качестве сбоя.  
  
 В этом разделе основан на [сериализации JSON](../../../../docs/framework/wcf/samples/json-serialization.md) образца.  
  
### <a name="to-define-the-data-contract-for-a-person"></a>Определение контракта для типа Person  
  
1.  Определите контракт данных для типа `Person`, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу и атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к элементам, которые требуется сериализовать. Дополнительные сведения о контрактах данных см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
    ```csharp  
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
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  Сериализуйте объект `Person` в поток памяти с помощью сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  С помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> запишите данные JSON в поток.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  Отобразите выходные данные JSON.  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>Десериализация экземпляра типа Person из формата JSON  
  
1.  Десериализуйте данные в кодировке JSON в новый экземпляр типа `Person` с помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  Отобразите результаты.  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a>Пример  
  
```csharp  
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
  
```csharp  
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
 [Поддержка JSON и других форматов передачи данных](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
