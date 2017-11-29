---
title: "Модуль форматирования веб-канала (JSON)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d6e1a2fe05d041d28d897e8effab3dfddb98845
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="feed-formatter-json"></a>Модуль форматирования веб-канала (JSON)
В этом примере показано, как сериализовать экземпляр класса <xref:System.ServiceModel.Syndication.SyndicationFeed> в формат нотации объектов JavaScript (JSON) с помощью пользовательских объектов <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
## <a name="architecture-of-the-sample"></a>Архитектура примера  
 В данном примере реализуется класс с именем `JsonFeedFormatter`, унаследованный от класса <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Класс `JsonFeedFormatter` использует класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> для чтения и записи данных в формате JSON. При внутренней обработке средство форматирования использует пользовательский набор типов контрактов данных с именами `JsonSyndicationFeed` и `JsonSyndicationItem` для контроля формата данных JSON, создаваемых сериализатором. Эти сведения реализации скрыты от конечного пользователя, что позволяет делать вызовы к стандартным классам <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
## <a name="writing-json-feeds"></a>Написание веб-каналов JSON  
 Веб-канал JSON можно написать, используя класс `JsonFeedFormatter` (реализованный в этом образце) с классом <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, как показано в следующем образце кода.  
  
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
  
## <a name="reading-a-json-feed"></a>Чтение веб-канала JSON  
 Получить объект <xref:System.ServiceModel.Syndication.SyndicationFeed> из потока данных в формате JSON можно с помощью класса `JsonFeedFormatter`, как показано в следующем примере кода.  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
  
## <a name="see-also"></a>См. также
