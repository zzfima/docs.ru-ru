---
title: "Сериализация JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Сериализация JSON
В этом образце показано, как с помощью объекта <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> сериализовать и десериализовать данные в формате JavaScript Object Notation \(JSON\).Механизм сериализации преобразует данные JSON в экземпляры типов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] и обратно в данные JSON.<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> поддерживает те же типы, что и <xref:System.Runtime.Serialization.DataContractSerializer>.Формат данных JSON бывает особенно полезен при написании веб\-приложений AJAX \(Asynchronous JavaScript and XML\).Поддержка технологии AJAX в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] оптимизирована для использования в ASP.NET AJAX с помощью элемента управления ScriptManager.Примеры использования [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с ASP.NET AJAX см. в разделе [AJAX Samples](http://msdn.microsoft.com/ru-ru/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце для демонстрации сериализации и десериализации используется контракт данных `Person`.  
  
```  
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
  
```  
Person p = new Person();  
//Set up Person object...  
MemoryStream stream1 = new MemoryStream();  
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
ser.WriteObject(stream1, p);  
  
```  
  
 Поток памяти содержит допустимые данные JSON.  
  
```  
{“age”:42,”name”:”John”}  
  
```  
  
 В этом образце показана десериализация данных JSON в объект.Для этого необходимо перемотать назад поток и вызвать метод `ReadObject`.  
  
```  
Person p2 = (Person)ser.ReadObject(stream1);  
```  
  
 Проверка объекта `p2` позволяет понять, что данные JSON были десериализованы правильно.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### Настройка, построение и выполнение образца  
  
1.  Выполните построение решения JsonSerialization.sln, как описано в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Запустите получившееся консольное приложение.  
  
## См. также