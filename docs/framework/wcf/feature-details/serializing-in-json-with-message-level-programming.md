---
title: "Сериализация в Json с помощью программирования на уровне сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfa8952c54f29d88cb4975c1924b9c3e94c1c226
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="aa124-102">Сериализация в Json с помощью программирования на уровне сообщений</span><span class="sxs-lookup"><span data-stu-id="aa124-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="aa124-103">WCF поддерживает сериализацию данных в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="aa124-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="aa124-104">В этом разделе описывается, как в WCF выполнить сериализацию типов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="aa124-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="aa124-105">Программирование типизированных сообщений</span><span class="sxs-lookup"><span data-stu-id="aa124-105">Typed Message Programming</span></span>  
 <span data-ttu-id="aa124-106"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> используется, когда к операции службы применяется атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="aa124-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="aa124-107">Оба атрибута позволяют задать формат запроса `RequestFormat` и формат ответа `ResponseFormat`.</span><span class="sxs-lookup"><span data-stu-id="aa124-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="aa124-108">Для использования формата JSON для запросов и ответов установите для обоих атрибутов значение `WebMessageFormat.Json`.</span><span class="sxs-lookup"><span data-stu-id="aa124-108">To use JSON for requests and responses set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="aa124-109">Для применения формата JSON необходимо использовать привязку <xref:System.ServiceModel.WebHttpBinding>, которая автоматически настраивает <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="aa124-109">In order to use JSON you must use the <xref:System.ServiceModel.WebHttpBinding> which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="aa124-110">Дополнительные сведения о сериализации WCF см. в разделе: [сериализации и десериализации](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [сериализация в Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa124-110">For more information about WCF serialization, see: [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md), [Serialization in Windows Communication Foundation](http://msdn.microsoft.com/magazine/cc163569.aspx).</span></span> <span data-ttu-id="aa124-111">Дополнительные сведения о JSON и WCF см [введение в службы RESTfull с WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Создание JSON-совместимых служб WCF в .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), и [Обзор REST в WCF](http://msdn.microsoft.com/netframework/dd547388).</span><span class="sxs-lookup"><span data-stu-id="aa124-111">For more information about JSON and WCF see [An Introduction to RESTfull Services with WCF](http://msdn.microsoft.com/magazine/dd315413.aspx), [Creating JSON-enabled WCF Services in .NET 3.5](http://www.pluralsight-training.net/community/blogs/fritz/archive/2008/01/31/50121.aspx), and [Overview of REST in WCF](http://msdn.microsoft.com/netframework/dd547388).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aa124-112">Для использования с JSON требуется привязка <xref:System.ServiceModel.WebHttpBinding> и поведение <xref:System.ServiceModel.Description.WebHttpBehavior>, которые не поддерживают связь по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="aa124-112">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="aa124-113">Службы, которые взаимодействуют с <xref:System.ServiceModel.WebHttpBinding> не поддерживают предоставление метаданных службы, поэтому вы не сможете использовать функции добавления служебной ссылки Visual Studio или средство командной строки svcutil для создания клиентского прокси.</span><span class="sxs-lookup"><span data-stu-id="aa124-113">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="aa124-114">Дополнительные сведения, как можно программным путем вызова служб, использующих <xref:System.ServiceModel.WebHttpBinding>, в разделе [как использовать службы REST с WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa124-114">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](http://blogs.msdn.com/b/pedram/archive/2008/04/21/how-to-consume-rest-services-with-wcf.aspx).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="aa124-115">Программирование нетипизированных сообщений</span><span class="sxs-lookup"><span data-stu-id="aa124-115">Untyped Message Programming</span></span>  
 <span data-ttu-id="aa124-116">При работе напрямую с объектами нетипизированного сообщения следует явно задать свойства нетипизированного сообщения для его сериализации в виде JSON.</span><span class="sxs-lookup"><span data-stu-id="aa124-116">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="aa124-117">В следующем фрагменте кода показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="aa124-117">The following code snippet shows how to do this.</span></span>  
  
```  
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa124-118">См. также</span><span class="sxs-lookup"><span data-stu-id="aa124-118">See Also</span></span>  
 [<span data-ttu-id="aa124-119">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="aa124-119">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="aa124-120">Автономная сериализация JSON</span><span class="sxs-lookup"><span data-stu-id="aa124-120">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="aa124-121">Сериализация JSON</span><span class="sxs-lookup"><span data-stu-id="aa124-121">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
