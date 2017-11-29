---
title: "Настройка отслеживания потока сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 15571ca2-bee2-47fb-ba10-fcbc09152ad0
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77a7148a0fc96c4a043a06fbfac7b139c7720d4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-message-flow-tracing"></a><span data-ttu-id="dac13-102">Настройка отслеживания потока сообщений</span><span class="sxs-lookup"><span data-stu-id="dac13-102">Configuring Message Flow Tracing</span></span>
<span data-ttu-id="dac13-103">Если включена трассировка действий [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], то стек [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] назначает логическим действиям полные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="dac13-103">When [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] activity tracing is enabled, End-To-End Activity IDs are assigned to logical activities throughout the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack.</span></span> <span data-ttu-id="dac13-104">Платформа [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] включает более высокопроизводительную версию этой функции, которая поддерживает работу со средством трассировкой событий для Windows, называемой трассировкой потока сообщений.</span><span class="sxs-lookup"><span data-stu-id="dac13-104">In [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)], there is now a higher performance version of this feature that works with Event Tracing for Windows (ETW) called message flow tracing.</span></span> <span data-ttu-id="dac13-105">При ее включении полные идентификаторы действий извлекаются (или назначаются при их отсутствии) и распространяются для всех событий трассировки, которые создаются после того, как канал декодировал сообщение.</span><span class="sxs-lookup"><span data-stu-id="dac13-105">When enabled, End-To-End activity IDs are taken from (or assigned to if empty) incoming messages and are propagated to all tracing events that are emitted after the message has been decoded by the channel.</span></span> <span data-ttu-id="dac13-106">Клиенты могут использовать эту функцию для воссоздания потоков сообщений с журналами трассировки от различных служб после декодирования.</span><span class="sxs-lookup"><span data-stu-id="dac13-106">Customers can use this feature to reconstruct message flows with trace logs from different services after decoding.</span></span>  
  
 <span data-ttu-id="dac13-107">Трассировку можно включить после обнаружения проблемы в работе приложения, а затем отключить после разрешения проблемы.</span><span class="sxs-lookup"><span data-stu-id="dac13-107">Tracing can be enabled after a problem is detected with the application and then disabled once the problem is resolved.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="dac13-108">Включение трассировки</span><span class="sxs-lookup"><span data-stu-id="dac13-108">Enabling Tracing</span></span>  
 <span data-ttu-id="dac13-109">Чтобы включить трассировку потока сообщений, установите элемент конфигурации .NET Framework 4 `messageFlowTracing` в значение `true`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dac13-109">You can enable message flow tracing by setting the .NET Framework 4 `messageFlowTracing` configuration element to `true`, as shown in the following example.</span></span>  
  
```xml  
<system.servicemodel>  
  <diagnostics>  
    <endToEndTracing propagateActivity="true" messageFlowTracing="true" />  
  </diagnostics>  
</system.servicemodel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="dac13-110">Поскольку элемент конфигурации `endToEndTracing` находится в файле Web.config, его нельзя динамично изменять таким же образом, как и трассировку событий Windows.</span><span class="sxs-lookup"><span data-stu-id="dac13-110">Because the `endToEndTracing` configuration element resides in a Web.config file, it cannot be dynamically configured in the same way as ETW.</span></span> <span data-ttu-id="dac13-111">Чтобы изменение параметра `endToEndTracing` вступило в силу, необходимо выполнить очистку приложения.</span><span class="sxs-lookup"><span data-stu-id="dac13-111">For the `endToEndTracing` configuration element to take effect, the application must be recycled.</span></span>  
  
 <span data-ttu-id="dac13-112">Действия связываются путем обмена идентификаторами действия.</span><span class="sxs-lookup"><span data-stu-id="dac13-112">Activities are correlated by the interchange of an identifier called the activity ID.</span></span> <span data-ttu-id="dac13-113">Эти идентификаторы являются идентификаторами GUID и формируются классом System.Diagnostics.CorrelationManager.</span><span class="sxs-lookup"><span data-stu-id="dac13-113">This identifier is a GUID, and is generated by the System.Diagnostics.CorrelationManager class.</span></span> <span data-ttu-id="dac13-114">При изменении идентификатора System.Diagnostics.Trace.CorrelationManager.ActivityID не забудьте вернуть идентификатору исходное значение, передавая управление обратно в код WCF.</span><span class="sxs-lookup"><span data-stu-id="dac13-114">If you manipulate System.Diagnostics.Trace.CorrelationManager.ActivityID, ensure that the value is set to original when execution control transfers back to WCF code.</span></span>  <span data-ttu-id="dac13-115">Кроме того, если используется асинхронная программная модель WCF, не забывайте передавать идентификатор System.Diagnostics.Trace.CorrelationManager.ActivityID между потоками.</span><span class="sxs-lookup"><span data-stu-id="dac13-115">Also, if you use an asynchronous WCF programming model ensure that System.Diagnostics.Trace.CorrelationManager.ActivityID is transferred between the threads.</span></span>  
  
## <a name="message-flow-tracing-and-rest-services"></a><span data-ttu-id="dac13-116">Трассировка потока сообщений и службы REST</span><span class="sxs-lookup"><span data-stu-id="dac13-116">Message Flow Tracing and REST Services</span></span>  
 <span data-ttu-id="dac13-117">Трассировка потока сообщений позволяет выполнять сквозную трассировку запроса.</span><span class="sxs-lookup"><span data-stu-id="dac13-117">Message flow tracing allows you to trace a request end to end.</span></span>  <span data-ttu-id="dac13-118">В службах на основе SOAP идентификатор действия отправляется в заголовке сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="dac13-118">With SOAP-based services an Activity ID is sent in a SOAP message header.</span></span> <span data-ttu-id="dac13-119">Запросы REST не содержат этот заголовок, поэтому взамен используется заголовок события HTTP.</span><span class="sxs-lookup"><span data-stu-id="dac13-119">REST requests do not contain this header so a special HTTP event header is used instead.</span></span> <span data-ttu-id="dac13-120">В следующем фрагменте кода показано, как можно программно получить значение идентификатора действия:</span><span class="sxs-lookup"><span data-stu-id="dac13-120">The following code snippet shows how you can programmatically retrieve the Activity ID value:</span></span>  
  
```csharp
Object output = null;
if (OperationContext.Current.IncomingMessageProperties.TryGetValue(HttpRequestMessageProperty.Name, out output))
{
   HttpRequestMessageProperty httpHeaders = output as HttpRequestMessageProperty;
   // Retrieve the Activity Id from the HTTP header    string e2eId = httpHeaders.Headers["E2EActivity"];
   // ...
}
```

 <span data-ttu-id="dac13-121">Можно программно добавить заголовок с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="dac13-121">You can programmatically add the header using the following code:</span></span>  
  
```csharp  
HttpContent content = new StreamContent(contentStream);  
Guid correlation = Guid.NewGuid();  
content.Headers.Add("E2EActivity", Convert.ToBase64String(correlation.ToByteArray()));  
```
