---
title: Сериализация JSON
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: bb38005c02e9b3e850282d2a81c2e17143657025
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989863"
---
# <a name="json-serialization"></a>Сериализация JSON
В этом образце показано, как с помощью объекта <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализовать и десериализовать данные в формате JavaScript Object Notation (JSON). Механизм сериализации преобразует данные JSON в экземпляры типов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] и обратно в данные JSON. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> поддерживает те же типы, что и <xref:System.Runtime.Serialization.DataContractSerializer>. Формат данных JSON бывает особенно полезен при написании веб-приложений AJAX (Asynchronous JavaScript and XML). Поддержка AJAX в Windows Communication Foundation (WCF), оптимизирован для использования с ASP.NET AJAX с помощью элемента управления ScriptManager. Примеры использования Windows Communication Foundation (WCF) с помощью ASP.NET AJAX см. в разделе [образцы AJAX](ajax.md).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
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
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, построение и выполнение примера  
  
1. Построение решения JsonSerialization.sln, как описано в разделе [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Запустите получившееся консольное приложение.  
