---
title: Использование арбитра контрактов данных
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 20ef713c67ee21aa8f7a92975bc6e6ce8798a087
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="using-a-data-contract-resolver"></a><span data-ttu-id="c2d47-102">Использование арбитра контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c2d47-102">Using a Data Contract Resolver</span></span>
<span data-ttu-id="c2d47-103">Арбитр контрактов данных позволяет динамически настраивать известные типы.</span><span class="sxs-lookup"><span data-stu-id="c2d47-103">A data contract resolver allows you to configure known types dynamically.</span></span> <span data-ttu-id="c2d47-104">Известные типы необходимы для сериализации или десериализации типов, не предусмотренных контрактом данных.</span><span class="sxs-lookup"><span data-stu-id="c2d47-104">Known types are required when serializing or deserializing a type not expected by a data contract.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c2d47-105"> об известных типах см. в разделе [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="c2d47-105"> known types, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="c2d47-106">Известные типы обычно задаются статически.</span><span class="sxs-lookup"><span data-stu-id="c2d47-106">Known types are normally specified statically.</span></span> <span data-ttu-id="c2d47-107">Это означает, что при реализации операции необходимо знать все типы, которые могут быть переданы операции.</span><span class="sxs-lookup"><span data-stu-id="c2d47-107">This means you would have to know all the possible types an operation may receive while implementing the operation.</span></span> <span data-ttu-id="c2d47-108">Существуют сценарии, в которых это не так, и важно иметь возможность динамического задания типов.</span><span class="sxs-lookup"><span data-stu-id="c2d47-108">There are scenarios in which this is not true and being able to specify known types dynamically is important.</span></span>  
  
## <a name="creating-a-data-contract-resolver"></a><span data-ttu-id="c2d47-109">Создание арбитра контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c2d47-109">Creating a Data Contract Resolver</span></span>  
 <span data-ttu-id="c2d47-110">Создание арбитра контрактов данных включает реализацию двух методов: <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> и <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2d47-110">Creating a data contract resolver involves implementing two methods, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> and <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span></span> <span data-ttu-id="c2d47-111">Эти методы реализуют обратные вызовы, используемые при сериализации и десериализации соответственно.</span><span class="sxs-lookup"><span data-stu-id="c2d47-111">These two methods implement callbacks that are used during serialization and deserialization, respectively.</span></span> <span data-ttu-id="c2d47-112">Метод <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> вызывается при сериализации, принимает тип контракта данных и сопоставляет его с именем `xsi:type` и пространством имен.</span><span class="sxs-lookup"><span data-stu-id="c2d47-112">The <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> method is invoked during serialization and takes a data contract type and maps it to an `xsi:type` name and namespace.</span></span> <span data-ttu-id="c2d47-113">Метод <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> вызывается при десериализации, принимает имя `xsi:type` и пространство имен и сопоставляется с типом контракта данных.</span><span class="sxs-lookup"><span data-stu-id="c2d47-113">The <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> method is invoked during deserialization and takes an `xsi:type` name and namespace and resolves it to a data contract type.</span></span> <span data-ttu-id="c2d47-114">Оба метода содержат параметр `knownTypeResolver`, который позволяет использовать в реализации арбитр известного типа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2d47-114">Both of these methods have a `knownTypeResolver` parameter that can be used to use the default known type resolver in your implementation.</span></span>  
  
 <span data-ttu-id="c2d47-115">В следующем примере показана реализация <xref:System.Runtime.Serialization.DataContractResolver> для сопоставления с типом контракта данных с именем `Customer`, производного от типа контракта данных `Person`.</span><span class="sxs-lookup"><span data-stu-id="c2d47-115">The following example shows how to implement a <xref:System.Runtime.Serialization.DataContractResolver> to map to and from a data contract type named `Customer` derived from a data contract type `Person`.</span></span>  
  
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
  
 <span data-ttu-id="c2d47-116">После определения <xref:System.Runtime.Serialization.DataContractResolver> его можно передать в конструктор <xref:System.Runtime.Serialization.DataContractSerializer>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c2d47-116">Once you have defined a <xref:System.Runtime.Serialization.DataContractResolver> you can use it by passing it to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor as shown in the following example.</span></span>  
  
```  
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 <span data-ttu-id="c2d47-117">Можно указать <xref:System.Runtime.Serialization.DataContractSerializer> в вызове метода <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A> или <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c2d47-117">You can specify a <xref:System.Runtime.Serialization.DataContractSerializer> in a call to the <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A> or <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A> methods, as shown in the following example.</span></span>  
  
```  
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 <span data-ttu-id="c2d47-118">Или же можно задать его для <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c2d47-118">Or you can set it on the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> as shown in the following example.</span></span>  
  
```  
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
  
 <span data-ttu-id="c2d47-119">Сопоставитель контрактов данных можно задать декларативно, реализовав атрибут, применяемый к службе.</span><span class="sxs-lookup"><span data-stu-id="c2d47-119">You can declaratively specify a data contract resolver by implementing an attribute that can be applied to a service.</span></span>  <span data-ttu-id="c2d47-120">Дополнительные сведения см. в разделе [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) образца.</span><span class="sxs-lookup"><span data-stu-id="c2d47-120">For more information, see the [KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) sample.</span></span> <span data-ttu-id="c2d47-121">Этот образец реализует атрибут с именем «KnownAssembly», добавляющий пользовательский арбитр контрактов данных для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="c2d47-121">This sample implements an attribute called "KnownAssembly" that adds a custom data contract resolver to the service’s behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d47-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d47-122">See Also</span></span>  
 [<span data-ttu-id="c2d47-123">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c2d47-123">Data Contract Known Types</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [<span data-ttu-id="c2d47-124">Пример DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="c2d47-124">DataContractSerializer Sample</span></span>](../../../../docs/framework/wcf/samples/datacontractserializer-sample.md)  
 [<span data-ttu-id="c2d47-125">Атрибут KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="c2d47-125">KnownAssemblyAttribute</span></span>](../../../../docs/framework/wcf/samples/knownassemblyattribute.md)
