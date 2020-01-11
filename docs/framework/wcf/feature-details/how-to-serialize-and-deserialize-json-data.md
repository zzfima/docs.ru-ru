---
title: Как использовать DataContractJsonSerializer
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 3cf8cc52587a64e7273ab9e0de0b1751d00827cf
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901217"
---
# <a name="how-to-use-datacontractjsonserializer"></a><span data-ttu-id="173d6-102">Как использовать DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="173d6-102">How to use DataContractJsonSerializer</span></span>

> [!NOTE]
> <span data-ttu-id="173d6-103">Эта статья посвящена <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="173d6-103">This article is about <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="173d6-104">В большинстве сценариев, в которых участвует сериализация и десериализация JSON, мы рекомендуем использовать интерфейсы API в [пространстве имен System. Text. JSON](../../../standard/serialization/system-text-json-overview.md).</span><span class="sxs-lookup"><span data-stu-id="173d6-104">For most scenarios that involve serializing and deserializing JSON, we recommend the APIs in the [System.Text.Json namespace](../../../standard/serialization/system-text-json-overview.md).</span></span>

<span data-ttu-id="173d6-105">JSON - эффективный формат кодирования данных, обеспечивающий быстрый обмен небольшими объемами данных между клиентскими браузерами и веб-службами с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="173d6-105">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>

<span data-ttu-id="173d6-106">В этой статье показано, как сериализовать объекты типа .NET в данные в кодировке JSON, а затем десериализовать данные в формате JSON обратно в экземпляры типов .NET.</span><span class="sxs-lookup"><span data-stu-id="173d6-106">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="173d6-107">В этом примере используется контракт данных для демонстрации сериализации и десериализации определяемого пользователем типа `Person` и используется <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="173d6-107">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<span data-ttu-id="173d6-108">Как правило, сериализация и десериализация JSON автоматически обрабатываются Windows Communication Foundation (WCF) при использовании типов контрактов данных в операциях службы, которые доступны через конечные точки с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="173d6-108">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="173d6-109">Однако в некоторых случаях может потребоваться непосредственная работа с данными JSON.</span><span class="sxs-lookup"><span data-stu-id="173d6-109">However, in some cases you may need to work with JSON data directly.</span></span>

<span data-ttu-id="173d6-110">Эта статья основана на [образце DataContractJsonSerializer](../samples/json-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="173d6-110">This article is based on the [DataContractJsonSerializer sample](../samples/json-serialization.md).</span></span>

## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="173d6-111">Определение контракта данных для типа Person</span><span class="sxs-lookup"><span data-stu-id="173d6-111">To define the data contract for a Person type</span></span>

1. <span data-ttu-id="173d6-112">Определите контракт данных для типа `Person`, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу и атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к элементам, которые требуется сериализовать.</span><span class="sxs-lookup"><span data-stu-id="173d6-112">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="173d6-113">Дополнительные сведения о контрактах данных см. в разделе [проектирование контрактов служб](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="173d6-113">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>

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

## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="173d6-114">Сериализация экземпляра типа Person в формат JSON</span><span class="sxs-lookup"><span data-stu-id="173d6-114">To serialize an instance of type Person to JSON</span></span>

> [!NOTE]
> <span data-ttu-id="173d6-115">Если ошибка возникает во время сериализации исходящего ответа на сервере или по какой-либо другой причине, она может не возвращаться клиенту в качестве ошибки.</span><span class="sxs-lookup"><span data-stu-id="173d6-115">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>

1. <span data-ttu-id="173d6-116">Создайте экземпляр типа `Person`.</span><span class="sxs-lookup"><span data-stu-id="173d6-116">Create an instance of the `Person` type.</span></span>

    ```csharp
    var p = new Person();
    p.name = "John";
    p.age = 42;
    ```

2. <span data-ttu-id="173d6-117">Сериализует объект `Person` в поток памяти с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="173d6-117">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

    ```csharp
    var stream1 = new MemoryStream();
    var ser = new DataContractJsonSerializer(typeof(Person));
    ```

3. <span data-ttu-id="173d6-118">С помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> запишите данные JSON в поток.</span><span class="sxs-lookup"><span data-stu-id="173d6-118">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>

    ```csharp
    ser.WriteObject(stream1, p);
    ```

4. <span data-ttu-id="173d6-119">Отобразите выходные данные JSON.</span><span class="sxs-lookup"><span data-stu-id="173d6-119">Show the JSON output.</span></span>

    ```csharp
    stream1.Position = 0;
    var sr = new StreamReader(stream1);
    Console.Write("JSON form of Person object: ");
    Console.WriteLine(sr.ReadToEnd());
    ```

## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="173d6-120">Десериализация экземпляра типа Person из формата JSON</span><span class="sxs-lookup"><span data-stu-id="173d6-120">To deserialize an instance of type Person from JSON</span></span>

1. <span data-ttu-id="173d6-121">Десериализуйте данные в кодировке JSON в новый экземпляр типа `Person` с помощью метода <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> сериализатора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="173d6-121">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

    ```csharp
    stream1.Position = 0;
    var p2 = (Person)ser.ReadObject(stream1);
    ```

2. <span data-ttu-id="173d6-122">Отобразите результаты.</span><span class="sxs-lookup"><span data-stu-id="173d6-122">Show the results.</span></span>

    ```csharp
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");
    ```

## <a name="example"></a><span data-ttu-id="173d6-123">Пример</span><span class="sxs-lookup"><span data-stu-id="173d6-123">Example</span></span>

```csharp
// Create a User object and serialize it to a JSON stream.
public static string WriteFromObject()
{
    // Create User object.
    var user = new User("Bob", 42);

    // Create a stream to serialize the object to.
    var ms = new MemoryStream();

    // Serializer the User object to the stream.
    var ser = new DataContractJsonSerializer(typeof(User));
    ser.WriteObject(ms, user);
    byte[] json = ms.ToArray();
    ms.Close();
    return Encoding.UTF8.GetString(json, 0, json.Length);
}

// Deserialize a JSON stream to a User object.
public static User ReadToObject(string json)
{
    var deserializedUser = new User();
    var ms = new MemoryStream(Encoding.UTF8.GetBytes(json));
    var ser = new DataContractJsonSerializer(deserializedUser.GetType());
    deserializedUser = ser.ReadObject(ms) as User;
    ms.Close();
    return deserializedUser;
}
```

> [!NOTE]
> <span data-ttu-id="173d6-124">Сериализатор JSON выдает исключение при сериализации контрактов данных, имеющих несколько элементов с одинаковым именем, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="173d6-124">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="173d6-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="173d6-125">See also</span></span>

- [<span data-ttu-id="173d6-126">Сериализация JSON в .NET</span><span class="sxs-lookup"><span data-stu-id="173d6-126">JSON serialization in .NET</span></span>](../../../standard/serialization/system-text-json-overview.md)
