---
title: Образец DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: d3456582d73640f1802c17d7f29f4931a6f920b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144634"
---
# <a name="datacontractjsonserializer-sample"></a>Образец DataContractJsonSerializer

> [!NOTE]
> Этот образец <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>предназначен для . Для большинства сценариев, связанных с сериализуем и десериализизацией JSON, мы рекомендуем AA в [пространстве имен System.Text.Json.](../../../standard/serialization/system-text-json-overview.md)

<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> поддерживает те же типы, что и <xref:System.Runtime.Serialization.DataContractSerializer>. Формат данных JSON бывает особенно полезен при написании веб-приложений AJAX (Asynchronous JavaScript and XML). Поддержка AJAX в Фонде связи Windows (WCF) оптимизирована для использования с ASP.NET AJAX через контроль ScriptManager. Примеры использования Windows Communication Foundation (WCF) с ASP.NET AJAX можно найти в [примере AJAX.](ajax.md)  
  
Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
В этом образце для демонстрации сериализации и десериализации используется контракт данных `Person`.  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 Чтобы сериализовать экземпляр типа `Person` в формат JSON, создайте объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и с помощью метода `WriteObject` запишите данные JSON в поток.  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 Поток памяти содержит допустимые данные JSON.
  
```json  
{"age":42,"name":"John"}  
```  
  
 В этом образце показана десериализация данных JSON в объект. Для этого необходимо перемотать назад поток и вызвать метод `ReadObject`.  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 Проверка объекта `p2` позволяет понять, что данные JSON были десериализованы правильно.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, построение и выполнение примера  
  
1. Создайте решение JsonSerialization.sln, как описано в [создании образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2. Запустите получившееся консольное приложение.  
