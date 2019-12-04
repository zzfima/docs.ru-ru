---
title: Модуль форматирования веб-канала (JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: dfdcd0920980e7e5cc1fe1c8910ee7cfbe59b5a0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715842"
---
# <a name="feed-formatter-json"></a><span data-ttu-id="a0f76-102">Модуль форматирования веб-канала (JSON)</span><span class="sxs-lookup"><span data-stu-id="a0f76-102">Feed Formatter (JSON)</span></span>
<span data-ttu-id="a0f76-103">В этом примере показано, как сериализовать экземпляр класса <xref:System.ServiceModel.Syndication.SyndicationFeed> в формат нотации объектов JavaScript (JSON) с помощью пользовательских объектов <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a0f76-103">This sample shows how to serialize an instance of a <xref:System.ServiceModel.Syndication.SyndicationFeed> class in JavaScript Object Notation (JSON) format by using a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> and the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="architecture-of-the-sample"></a><span data-ttu-id="a0f76-104">Архитектура примера</span><span class="sxs-lookup"><span data-stu-id="a0f76-104">Architecture of the Sample</span></span>  
 <span data-ttu-id="a0f76-105">В данном примере реализуется класс с именем `JsonFeedFormatter`, унаследованный от класса <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="a0f76-105">The sample implements a class named `JsonFeedFormatter` that inherits from <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="a0f76-106">Класс `JsonFeedFormatter` использует класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> для чтения и записи данных в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="a0f76-106">The `JsonFeedFormatter` class relies on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to read and write the data in JSON format.</span></span> <span data-ttu-id="a0f76-107">При внутренней обработке средство форматирования использует пользовательский набор типов контрактов данных с именами `JsonSyndicationFeed` и `JsonSyndicationItem` для контроля формата данных JSON, создаваемых сериализатором.</span><span class="sxs-lookup"><span data-stu-id="a0f76-107">Internally, the formatter uses a custom set of data contract types named `JsonSyndicationFeed` and `JsonSyndicationItem` to control the format of the JSON data produced by the serializer.</span></span> <span data-ttu-id="a0f76-108">Эти сведения реализации скрыты от конечного пользователя, что позволяет делать вызовы к стандартным классам <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="a0f76-108">These implementation details are hidden from the end user, allowing calls to be made against the standard <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> classes.</span></span>  
  
## <a name="writing-json-feeds"></a><span data-ttu-id="a0f76-109">Написание веб-каналов JSON</span><span class="sxs-lookup"><span data-stu-id="a0f76-109">Writing JSON feeds</span></span>  
 <span data-ttu-id="a0f76-110">Веб-канал JSON можно написать, используя класс `JsonFeedFormatter` (реализованный в этом образце) с классом <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="a0f76-110">Writing a JSON feed can be accomplished by using the `JsonFeedFormatter` (implemented in this sample) with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> as shown in the following sample code.</span></span>  
  
```csharp  
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
  
## <a name="reading-a-json-feed"></a><span data-ttu-id="a0f76-111">Чтение веб-канала JSON</span><span class="sxs-lookup"><span data-stu-id="a0f76-111">Reading a JSON feed</span></span>  
 <span data-ttu-id="a0f76-112">Получить объект <xref:System.ServiceModel.Syndication.SyndicationFeed> из потока данных в формате JSON можно с помощью класса `JsonFeedFormatter`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="a0f76-112">Obtaining a <xref:System.ServiceModel.Syndication.SyndicationFeed> from a stream of JSON-formatted data can be accomplished with the `JsonFeedFormatter` as show in the following code.</span></span>  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a0f76-113">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="a0f76-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a0f76-114">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a0f76-114">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a0f76-115">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a0f76-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a0f76-116">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a0f76-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a0f76-117">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0f76-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a0f76-118">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a0f76-118">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="a0f76-119">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="a0f76-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a0f76-120">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="a0f76-120">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
