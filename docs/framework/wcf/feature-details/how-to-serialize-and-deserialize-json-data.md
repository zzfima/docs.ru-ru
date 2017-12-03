---
title: "Практическое руководство. Сериализация и десериализация данных JSON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4fd768a3a254616dc5dd8b5127ec7f794b71159
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="d8010-102">Практическое руководство. Сериализация и десериализация данных JSON</span><span class="sxs-lookup"><span data-stu-id="d8010-102">How to: Serialize and Deserialize JSON Data</span></span>
<span data-ttu-id="d8010-103">JSON - эффективный формат кодирования данных, обеспечивающий быстрый обмен небольшими объемами данных между клиентскими браузерами и веб-службами с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="d8010-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="d8010-104">В этом разделе показано, как сериализовать объекты типов .NET в данные с кодировкой JSON, а затем десериализовать формат JSON обратно в экземпляры типов .NET с помощью сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d8010-104">This topic demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="d8010-105">В этом примере показана сериализация и десериализация пользовательского типа `Person` с помощью контракта данных.</span><span class="sxs-lookup"><span data-stu-id="d8010-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type.</span></span>  
  
 <span data-ttu-id="d8010-106">Обычно сериализация и десериализация JSON обрабатывается автоматически в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] при использовании типов контрактов данных в операциях службы, предоставляемых через конечные точки с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="d8010-106">Normally, JSON serialization and deserialization is handled automatically by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="d8010-107">Впрочем, в некоторых случаях может потребоваться работать с данными JSON напрямую. Именно этот сценарий рассмотрен в данном примере.</span><span class="sxs-lookup"><span data-stu-id="d8010-107">However, in some cases you may need to work with JSON data directly - this is the scenario that this topic demonstrates.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8010-108">Если возникает ошибка при сериализации исходящего ответа на сервере или операция ответа выдает исключение по какой-либо другой причине, такая ошибка может не вернуться на клиент в качестве сбоя.</span><span class="sxs-lookup"><span data-stu-id="d8010-108">If an error occurs during serialization of an outgoing reply on the server or the reply operation throws an exception for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="d8010-109">В этом разделе основан на [сериализации JSON](../../../../docs/framework/wcf/samples/json-serialization.md) образца.</span><span class="sxs-lookup"><span data-stu-id="d8010-109">This topic is based on the [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) sample.</span></span>  
  
### <a name="to-define-the-data-contract-for-a-person"></a><span data-ttu-id="d8010-110">Определение контракта для типа Person</span><span class="sxs-lookup"><span data-stu-id="d8010-110">To define the data contract for a Person</span></span>  
  
1.  <span data-ttu-id="d8010-111">Определите контракт данных для типа `Person`, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу и атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к элементам, которые требуется сериализовать.</span><span class="sxs-lookup"><span data-stu-id="d8010-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d8010-112">контрактах данных см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="d8010-112"> data contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
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
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="d8010-113">Сериализация экземпляра типа Person в формат JSON</span><span class="sxs-lookup"><span data-stu-id="d8010-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="d8010-114">Создайте экземпляр типа `Person`.</span><span class="sxs-lookup"><span data-stu-id="d8010-114">Create an instance of the `Person` type.</span></span>  
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="d8010-115">Сериализуйте объект `Person` в поток памяти с помощью сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d8010-115">Serialize the `Person` object to a memory stream using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="d8010-116">С помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> запишите данные JSON в поток.</span><span class="sxs-lookup"><span data-stu-id="d8010-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="d8010-117">Отобразите выходные данные JSON.</span><span class="sxs-lookup"><span data-stu-id="d8010-117">Show the JSON output.</span></span>  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="d8010-118">Десериализация экземпляра типа Person из формата JSON</span><span class="sxs-lookup"><span data-stu-id="d8010-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="d8010-119">Десериализуйте данные в кодировке JSON в новый экземпляр типа `Person` с помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="d8010-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="d8010-120">Отобразите результаты.</span><span class="sxs-lookup"><span data-stu-id="d8010-120">Show the results.</span></span>  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a><span data-ttu-id="d8010-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d8010-121">Example</span></span>  
  
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
>  <span data-ttu-id="d8010-122">Сериализатор JSON выдает исключение при сериализации контрактов данных, имеющих несколько элементов с одинаковым именем, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="d8010-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8010-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d8010-123">See Also</span></span>  
 [<span data-ttu-id="d8010-124">Автономная сериализация JSON</span><span class="sxs-lookup"><span data-stu-id="d8010-124">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="d8010-125">Поддержка JSON и других данных форматов передачи</span><span class="sxs-lookup"><span data-stu-id="d8010-125">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
