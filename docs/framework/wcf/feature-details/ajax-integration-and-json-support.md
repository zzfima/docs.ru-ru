---
title: Интеграция с AJAX и поддержка JSON
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0d62da8cf67fb8f996f341018c39146b51e308c3
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="c139c-102">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="c139c-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="c139c-103">Поддержка [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] формата данных асинхронных сценариев JavaScript и XML (AJAX), а также JavaScript Object Notation (JSON) ASP.NET позволяет клиентам AJAX использовать операции служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c139c-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span> <span data-ttu-id="c139c-104">Клиенты AJAX представляют собой веб-страницы, на которых выполняется код JavaScript и которые обращаются к этим службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="c139c-104">AJAX clients are Web pages running JavaScript code and accessing these [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using HTTP requests.</span></span> <span data-ttu-id="c139c-105">В этом разделе приведены сведения о такой поддержке и способах ее реализации.</span><span class="sxs-lookup"><span data-stu-id="c139c-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="c139c-106">Дополнительные сведения о ASP.NET AJAX и интеграции с ASP.NET 2.0 см. в разделе [Общие сведения о ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="c139c-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c139c-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c139c-107">In This Section</span></span>  
 [<span data-ttu-id="c139c-108">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="c139c-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="c139c-109">Описывается, как клиенты AJAX могут использовать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], добавляя соответствующую конечную точку AJAX через конфигурацию или с помощью производства узла службы, настроенного на создание узла службы, который предназначен для автоматической настройки конечной точки AJAX.</span><span class="sxs-lookup"><span data-stu-id="c139c-109">Describes how an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="c139c-110">Создание служб WCF AJAX без использования ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c139c-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="c139c-111">Описывается, как создать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], не используя ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c139c-111">Describes how to create an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="c139c-112">Поддержка JSON и других форматов передачи данных</span><span class="sxs-lookup"><span data-stu-id="c139c-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="c139c-113">Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX (вместо XML).</span><span class="sxs-lookup"><span data-stu-id="c139c-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="c139c-114">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="c139c-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="c139c-115">Описывается, как перенести веб-службу ASP.NET с поддержкой AJAX в веб-службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c139c-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c139c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c139c-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="c139c-117">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="c139c-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
