---
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: 716bcb2bb43656051beffb15da9c7a988942ecd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183793"
---
# <a name="datacontractresolver"></a>DataContractResolver
В этом образце показано, как можно настроить процессы сериализации и десериализации с помощью класса <xref:System.Runtime.Serialization.DataContractResolver>. Этот образец демонстрирует применение класса DataContractResolver для сопоставления типов CLR с представлением xsi:type во время сериализации и десериализации.

## <a name="sample-details"></a>Подробные сведения об образце
 В образце определяются следующие типы CLR.

```csharp
using System;
using System.Runtime.Serialization;

namespace Types
{
    [DataContract]
    public class Customer
    {
        [DataMember]
        public string Name { get; set; }
    }

    [DataContract]
    public class VIPCustomer : Customer
    {
        [DataMember]
        public string VipInfo { get; set; }
    }

    [DataContract]
    public class RegularCustomer : Customer
    {
    }

    [DataContract]
    public class PreferredVIPCustomer : VIPCustomer
    {
    }
}
```

 Образец загружает сборку, извлекает каждый из следующих типов, а затем сериализует и десериализует их. Как показано в следующем примере, класс <xref:System.Runtime.Serialization.DataContractResolver> участвует в процессе сериализации, передавая экземпляр производного класса <xref:System.Runtime.Serialization.DataContractResolver> в конструктор <xref:System.Runtime.Serialization.DataContractSerializer>.

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 Затем образец сериализует типы CLR, как показано в следующем примере программного кода.

```csharp
Assembly assembly = Assembly.Load(new AssemblyName("Types"));

public void serialize(Type type)
{
    Object instance = Activator.CreateInstance(type);

    Console.WriteLine("----------------------------------------");
    Console.WriteLine();
    Console.WriteLine("Serializing type: {0}", type.Name);
    Console.WriteLine();
    this.buffer = new StringBuilder();
    using (XmlWriter xmlWriter = XmlWriter.Create(this.buffer))
    {
        try
        {
            this.serializer.WriteObject(xmlWriter, instance);
        }
        catch (SerializationException error)
        {
            Console.WriteLine(error.ToString());
        }
    }
    Console.WriteLine(this.buffer.ToString());
}
```

 Затем образец десериализует типы xsi:type, как показано в следующем примере программного кода.

```csharp
public void deserialize(Type type)
{
    Console.WriteLine();
    Console.WriteLine("Deserializing type: {0}", type.Name);
    Console.WriteLine();
    using (XmlReader xmlReader = XmlReader.Create(new StringReader(this.buffer.ToString())))
    {
        Object obj = this.serializer.ReadObject(xmlReader);
    }
}
```

 Поскольку пользовательский класс <xref:System.Runtime.Serialization.DataContractResolver> передается в конструктор <xref:System.Runtime.Serialization.DataContractSerializer>, во время сериализации вызывается метод <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A>, чтобы сопоставить тип CLR с эквивалентным элементом `xsi:type`. Аналогично во время десериализации вызывается метод <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>, чтобы сопоставить элемент `xsi:type` с эквивалентным типом CLR. В этом образце <xref:System.Runtime.Serialization.DataContractResolver> определен, как показано в следующем примере.

 В следующем примере кода представлен класс, являющийся производным от <xref:System.Runtime.Serialization.DataContractResolver>.

```csharp
class MyDataContractResolver : DataContractResolver
{
    private Dictionary<string, XmlDictionaryString> dictionary = new Dictionary<string, XmlDictionaryString>();
    Assembly assembly;

    public MyDataContractResolver(Assembly assembly)
    {
        this.assembly = assembly;
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        XmlDictionaryString tName;
        XmlDictionaryString tNamespace;
        if (dictionary.TryGetValue(typeName, out tName) && dictionary.TryGetValue(typeNamespace, out tNamespace))
        {
            return this.assembly.GetType(tNamespace.Value + "." + tName.Value);
        }
        else
        {
            return null;
        }
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        string name = dataContractType.Name;
        string namesp = dataContractType.Namespace;
        typeName = new XmlDictionaryString(XmlDictionary.Empty, name, 0);
        typeNamespace = new XmlDictionaryString(XmlDictionary.Empty, namesp, 0);
        if (!dictionary.ContainsKey(dataContractType.Name))
        {
            dictionary.Add(name, typeName);
        }
        if (!dictionary.ContainsKey(dataContractType.Namespace))
        {
            dictionary.Add(namesp, typeNamespace);
        }
    }
}
```

 Будучи частью образца, проект «Type» создает сборку со всеми типами, которые используются в этом образце. Используйте этот проект для добавления, удаления или изменения типов, которые будут сериализованы.

#### <a name="to-use-this-sample"></a>Использование этого образца

1. Используя Visual Studio 2012, откройте файл решения DCRSample.sln.

2. Чтобы запустить решение, нажмите клавишу F5.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a>См. также раздел

- [Использование арбитра контрактов данных](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)
