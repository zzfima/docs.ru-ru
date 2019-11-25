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
# <a name="using-a-data-contract-resolver"></a>Использование арбитра контрактов данных
Арбитр контрактов данных позволяет динамически настраивать известные типы. Известные типы необходимы для сериализации или десериализации типов, не предусмотренных контрактом данных. Дополнительные сведения об известных типах см. в разделе [Data Contract известные типы](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md). Известные типы обычно задаются статически. Это означает, что при реализации операции необходимо знать все типы, которые могут быть переданы операции. Существуют сценарии, в которых это не так, и важно иметь возможность динамического задания типов.  
  
## <a name="creating-a-data-contract-resolver"></a>Создание арбитра контрактов данных  
 Создание арбитра контрактов данных включает реализацию двух методов: <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> и <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>. Эти методы реализуют обратные вызовы, используемые при сериализации и десериализации соответственно. Метод <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> вызывается при сериализации, принимает тип контракта данных и сопоставляет его с именем `xsi:type` и пространством имен. Метод <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> вызывается при десериализации, принимает имя `xsi:type` и пространство имен и сопоставляется с типом контракта данных. Оба метода содержат параметр `knownTypeResolver`, который позволяет использовать в реализации арбитр известного типа по умолчанию.  
  
 В следующем примере показана реализация <xref:System.Runtime.Serialization.DataContractResolver> для сопоставления с типом контракта данных с именем `Customer`, производного от типа контракта данных `Person`.  
  
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
  
 После определения <xref:System.Runtime.Serialization.DataContractResolver> его можно передать в конструктор <xref:System.Runtime.Serialization.DataContractSerializer>, как показано в следующем примере.  
  
```csharp
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 Можно указать <xref:System.Runtime.Serialization.DataContractResolver> в вызове метода <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> или <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType>, как показано в следующем примере.  
  
```csharp
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 Или же можно задать его для <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, как показано в следующем примере.  
  
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
  
 Сопоставитель контрактов данных можно задать декларативно, реализовав атрибут, применяемый к службе.  Дополнительные сведения см. в примере [кновнассембляттрибуте](../../../../docs/framework/wcf/samples/knownassemblyattribute.md) . В этом примере реализуется атрибут с именем «Кновнассембли», который добавляет пользовательский сопоставитель контракта данных к поведению службы.  
  
## <a name="see-also"></a>См. также

- [Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Пример DataContractSerializer](../../../../docs/framework/wcf/samples/datacontractserializer-sample.md)
- [Атрибут KnownAssemblyAttribute](../../../../docs/framework/wcf/samples/knownassemblyattribute.md)
