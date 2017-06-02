---
title: "Модуль форматирования веб-канала (JSON) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Модуль форматирования веб-канала (JSON)
В этом примере показано, как сериализовать экземпляр класса <xref:System.ServiceModel.Syndication.SyndicationFeed> в формат нотации объектов JavaScript \(JSON\) с помощью пользовательских объектов <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## Архитектура примера  
 В данном примере реализуется класс с именем `JsonFeedFormatter`, унаследованный от класса <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.  Класс `JsonFeedFormatter` использует класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> для чтения и записи данных в формате JSON.  При внутренней обработке средство форматирования использует пользовательский набор типов контрактов данных с именами `JsonSyndicationFeed` и `JsonSyndicationItem` для контроля формата данных JSON, создаваемых сериализатором.  Эти сведения реализации скрыты от конечного пользователя, что позволяет делать вызовы к стандартным классам <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
## Написание веб\-каналов JSON  
 Веб\-канал JSON можно написать, используя класс `JsonFeedFormatter` \(реализованный в этом образце\) с классом <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, как показано в следующем образце кода.  
  
```  
//Basic feed with sample data  
SyndicationFeed feed = new SyndicationFeed("Custom JSON feed", "A Syndication extensibility sample", null);  
feed.LastUpdatedTime = DateTime.Now;  
feed.Items = from s in new string[] { "hello", "world" }  
select new SyndicationItem()  
{  
    Summary = SyndicationContent.CreatePlaintextContent(s)  
};  
  
//Write the feed out to a MemoryStream in JSON format  
DataContractJsonSerializer writeSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));  
writeSerializer.WriteObject(stream, new JsonFeedFormatter(feed));  
  
```  
  
## Чтение веб\-канала JSON  
 Получить объект <xref:System.ServiceModel.Syndication.SyndicationFeed> из потока данных в формате JSON можно с помощью класса `JsonFeedFormatter`, как показано в следующем примере кода.  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
  
## См. также