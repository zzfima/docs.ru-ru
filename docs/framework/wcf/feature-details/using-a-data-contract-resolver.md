---
title: Использование арбитра контрактов данных
ms.date: 03/30/2017
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
ms.openlocfilehash: d9082d2979cf9bd0837635af567d69ef34c2e312
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975973"
---
# <a name="using-a-data-contract-resolver"></a><span data-ttu-id="02738-102">Использование арбитра контрактов данных</span><span class="sxs-lookup"><span data-stu-id="02738-102">Using a Data Contract Resolver</span></span>
<span data-ttu-id="02738-103">Арбитр контрактов данных позволяет динамически настраивать известные типы.</span><span class="sxs-lookup"><span data-stu-id="02738-103">A data contract resolver allows you to configure known types dynamically.</span></span> <span data-ttu-id="02738-104">Известные типы необходимы для сериализации или десериализации типов, не предусмотренных контрактом данных.</span><span class="sxs-lookup"><span data-stu-id="02738-104">Known types are required when serializing or deserializing a type not expected by a data contract.</span></span> <span data-ttu-id="02738-105">Дополнительные сведения об известных типах см. в разделе [Data Contract известные типы](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="02738-105">For more information about known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="02738-106">Известные типы обычно задаются статически.</span><span class="sxs-lookup"><span data-stu-id="02738-106">Known types are normally specified statically.</span></span> <span data-ttu-id="02738-107">Это означает, что при реализации операции необходимо знать все типы, которые могут быть переданы операции.</span><span class="sxs-lookup"><span data-stu-id="02738-107">This means you would have to know all the possible types an operation may receive while implementing the operation.</span></span> <span data-ttu-id="02738-108">Существуют сценарии, в которых это не так, и важно иметь возможность динамического задания типов.</span><span class="sxs-lookup"><span data-stu-id="02738-108">There are scenarios in which this is not true and being able to specify known types dynamically is important.</span></span>  
  
## <a name="creating-a-data-contract-resolver"></a><span data-ttu-id="02738-109">Создание арбитра контрактов данных</span><span class="sxs-lookup"><span data-stu-id="02738-109">Creating a Data Contract Resolver</span></span>  
 <span data-ttu-id="02738-110">Создание арбитра контрактов данных включает реализацию двух методов: <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> и <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span><span class="sxs-lookup"><span data-stu-id="02738-110">Creating a data contract resolver involves implementing two methods, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> and <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span></span> <span data-ttu-id="02738-111">Эти методы реализуют обратные вызовы, используемые при сериализации и десериализации соответственно.</span><span class="sxs-lookup"><span data-stu-id="02738-111">These two methods implement callbacks that are used during serialization and deserialization, respectively.</span></span> <span data-ttu-id="02738-112">Метод <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> вызывается при сериализации, принимает тип контракта данных и сопоставляет его с именем `xsi:type` и пространством имен.</span><span class="sxs-lookup"><span data-stu-id="02738-112">The <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> method is invoked during serialization and takes a data contract type and maps it to an `xsi:type` name and namespace.</span></span> <span data-ttu-id="02738-113">Метод <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> вызывается при десериализации, принимает имя `xsi:type` и пространство имен и сопоставляется с типом контракта данных.</span><span class="sxs-lookup"><span data-stu-id="02738-113">The <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> method is invoked during deserialization and takes an `xsi:type` name and namespace and resolves it to a data contract type.</span></span> <span data-ttu-id="02738-114">Оба метода содержат параметр `knownTypeResolver`, который позволяет использовать в реализации арбитр известного типа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="02738-114">Both of these methods have a `knownTypeResolver` parameter that can be used to use the default known type resolver in your implementation.</span></span>  
  
 <span data-ttu-id="02738-115">В следующем примере показана реализация <xref:System.Runtime.Serialization.DataContractResolver> для сопоставления с типом контракта данных с именем `Customer`, производного от типа контракта данных `Person`.</span><span class="sxs-lookup"><span data-stu-id="02738-115">The following example shows how to implement a <xref:System.Runtime.Serialization.DataContractResolver> to map to and from a data contract type named `Customer` derived from a data contract type `Person`.</span></span>  
  
```csharp  
public class MyCustomerResolver : DataContractResolver  
{  
    public override bool TryResolveType(Type dataContractType, Type declaredType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        if (dataContractType == typeof(Customer))  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add("SomeCustomer");  
            typeNamespace = dictionary.Add("http://tempuri.com");  
            return true;  
        }  
        else  
        {  
            return knownTypeResolver.TryResolveType(dataContractType, declaredType, null, out typeName, out typeNamespace);  
        }  
    }  
  
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        if (typeName == "SomeCustomer" && typeNamespace == "http://tempuri.com")  
        {  
            return typeof(Customer);  
        }  
        else  
        {  
            return knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="02738-116">После определения <xref:System.Runtime.Serialization.DataContractResolver> его можно передать в конструктор <xref:System.Runtime.Serialization.DataContractSerializer>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="02738-116">Once you have defined a <xref:System.Runtime.Serialization.DataContractResolver> you can use it by passing it to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor as shown in the following example.</span></span>  
  
```csharp
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 <span data-ttu-id="02738-117">Можно указать <xref:System.Runtime.Serialization.DataContractResolver> в вызове метода <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> или <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="02738-117">You can specify a <xref:System.Runtime.Serialization.DataContractResolver> in a call to the <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> or <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType> methods, as shown in the following example.</span></span>  
  
```csharp
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 <span data-ttu-id="02738-118">Или же можно задать его для <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="02738-118">Or you can set it on the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> as shown in the following example.</span></span>  
  
```csharp
ServiceHost host = new ServiceHost(typeof(MyService));  
  
ContractDescription cd = host.Description.Endpoints[0].Contract;  
OperationDescription myOperationDescription = cd.Operations.Find("Echo");  
  
DataContractSerializerOperationBehavior serializerBehavior = myOperationDescription.Behaviors.Find<DataContractSerializerOperationBehavior>();  
if (serializerBehavior == null)  
{  
    serializerBehavior = new DataContractSerializerOperationBehavior(myOperationDescription);  
    myOperationDescription.Behaviors.Add(serializerBehavior);  
}  
  
SerializerBehavior.DataContractResolver = new MyCustomerResolver();  
```  
  
 <span data-ttu-id="02738-119">Сопоставитель контрактов данных можно задать декларативно, реализовав атрибут, применяемый к службе.</span><span class="sxs-lookup"><span data-stu-id="02738-119">You can declaratively specify a data contract resolver by implementing an attribute that can be applied to a service.</span></span>  <span data-ttu-id="02738-120">Дополнительные сведения см. в примере [кновнассембляттрибуте](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) .</span><span class="sxs-lookup"><span data-stu-id="02738-120">For more information, see the [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) sample.</span></span> <span data-ttu-id="02738-121">В этом примере реализуется атрибут с именем «Кновнассембли», который добавляет пользовательский сопоставитель контракта данных к поведению службы.</span><span class="sxs-lookup"><span data-stu-id="02738-121">This sample implements an attribute called "KnownAssembly" that adds a custom data contract resolver to the service’s behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02738-122">См. также</span><span class="sxs-lookup"><span data-stu-id="02738-122">See also</span></span>

- [<span data-ttu-id="02738-123">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="02738-123">Data Contract Known Types</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="02738-124">Пример DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="02738-124">DataContractSerializer Sample</span></span>](../../../../docs/framework/wcf/samples/datacontractserializer-sample.md)
- [<span data-ttu-id="02738-125">Атрибут KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="02738-125">KnownAssemblyAttribute</span></span>](../../../../docs/framework/wcf/samples/knownassemblyattribute.md)
