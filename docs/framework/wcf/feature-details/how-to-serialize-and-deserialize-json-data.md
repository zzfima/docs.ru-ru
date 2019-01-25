---
title: Как выполнить Сериализация и десериализация данных JSON
ms.date: 03/30/2017
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 797b29fd7ddecd3e3ed85f8cb3a6df93044942ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704346"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="caf52-102">Как выполнить Сериализация и десериализация данных JSON</span><span class="sxs-lookup"><span data-stu-id="caf52-102">How to: Serialize and Deserialize JSON Data</span></span>
<span data-ttu-id="caf52-103">JSON - эффективный формат кодирования данных, обеспечивающий быстрый обмен небольшими объемами данных между клиентскими браузерами и веб-службами с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="caf52-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="caf52-104">В этом разделе показано, как сериализовать объекты типов .NET в данные с кодировкой JSON, а затем десериализовать формат JSON обратно в экземпляры типов .NET с помощью сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="caf52-104">This topic demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="caf52-105">В этом примере показана сериализация и десериализация пользовательского типа `Person` с помощью контракта данных.</span><span class="sxs-lookup"><span data-stu-id="caf52-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type.</span></span>  
  
 <span data-ttu-id="caf52-106">Как правило сериализации и десериализации JSON выполняется автоматически с Windows Communication Foundation (WCF) при использовании типов контрактов данных в операции службы, которые предоставляются через конечные точки с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="caf52-106">Normally, JSON serialization and deserialization is handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="caf52-107">Впрочем, в некоторых случаях может потребоваться работать с данными JSON напрямую. Именно этот сценарий рассмотрен в данном примере.</span><span class="sxs-lookup"><span data-stu-id="caf52-107">However, in some cases you may need to work with JSON data directly - this is the scenario that this topic demonstrates.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="caf52-108">Если возникает ошибка при сериализации исходящего ответа на сервере или операция ответа выдает исключение по какой-либо другой причине, такая ошибка может не вернуться на клиент в качестве сбоя.</span><span class="sxs-lookup"><span data-stu-id="caf52-108">If an error occurs during serialization of an outgoing reply on the server or the reply operation throws an exception for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="caf52-109">Этот раздел основан на [сериализации JSON](../../../../docs/framework/wcf/samples/json-serialization.md) образца.</span><span class="sxs-lookup"><span data-stu-id="caf52-109">This topic is based on the [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) sample.</span></span>  
  
### <a name="to-define-the-data-contract-for-a-person"></a><span data-ttu-id="caf52-110">Определение контракта для типа Person</span><span class="sxs-lookup"><span data-stu-id="caf52-110">To define the data contract for a Person</span></span>  
  
1.  <span data-ttu-id="caf52-111">Определите контракт данных для типа `Person`, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу и атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к элементам, которые требуется сериализовать.</span><span class="sxs-lookup"><span data-stu-id="caf52-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="caf52-112">Дополнительные сведения о контрактах данных см. в разделе [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="caf52-112">For more information about data contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
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
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="caf52-113">Сериализация экземпляра типа Person в формат JSON</span><span class="sxs-lookup"><span data-stu-id="caf52-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="caf52-114">Создайте экземпляр типа `Person`.</span><span class="sxs-lookup"><span data-stu-id="caf52-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="caf52-115">Сериализуйте объект `Person` в поток памяти с помощью сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="caf52-115">Serialize the `Person` object to a memory stream using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="caf52-116">С помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> запишите данные JSON в поток.</span><span class="sxs-lookup"><span data-stu-id="caf52-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="caf52-117">Отобразите выходные данные JSON.</span><span class="sxs-lookup"><span data-stu-id="caf52-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="caf52-118">Десериализация экземпляра типа Person из формата JSON</span><span class="sxs-lookup"><span data-stu-id="caf52-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="caf52-119">Десериализуйте данные в кодировке JSON в новый экземпляр типа `Person` с помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="caf52-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="caf52-120">Отобразите результаты.</span><span class="sxs-lookup"><span data-stu-id="caf52-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="caf52-121">Пример</span><span class="sxs-lookup"><span data-stu-id="caf52-121">Example</span></span>  
  
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
>  <span data-ttu-id="caf52-122">Сериализатор JSON выдает исключение при сериализации контрактов данных, имеющих несколько элементов с одинаковым именем, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="caf52-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="caf52-123">См. также</span><span class="sxs-lookup"><span data-stu-id="caf52-123">See also</span></span>
- [<span data-ttu-id="caf52-124">Автономная сериализация JSON</span><span class="sxs-lookup"><span data-stu-id="caf52-124">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [<span data-ttu-id="caf52-125">Поддержка JSON и других форматов передачи данных</span><span class="sxs-lookup"><span data-stu-id="caf52-125">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
