---
title: Интеграция с AJAX и поддержка JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: 0b392044db3fbc926bf77ac305ece294880216d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488833"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="362d5-102">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="362d5-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="362d5-103">Поддержка Windows Communication Foundation (WCF) для ASP.NET асинхронных скриптов JavaScript и XML (AJAX) и формат JavaScript Object Notation (JSON) данных позволяют службам WCF предоставлять операции клиентам AJAX.</span><span class="sxs-lookup"><span data-stu-id="362d5-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="362d5-104">Клиенты AJAX представляют собой веб-страницы которых выполняется код JavaScript и доступ к этих служб WCF, с помощью HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="362d5-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="362d5-105">В этом разделе приведены сведения о такой поддержке и способах ее реализации.</span><span class="sxs-lookup"><span data-stu-id="362d5-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="362d5-106">Дополнительные сведения о ASP.NET AJAX и интеграции с ASP.NET 2.0 см. в разделе [Общие сведения о ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="362d5-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="362d5-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="362d5-107">In This Section</span></span>  
 [<span data-ttu-id="362d5-108">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="362d5-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="362d5-109">Описывает, как службы WCF в доступные клиентам AJAX, добавив соответствующую конечную точку AJAX, либо через конфигурацию или с помощью фабрики узла службы, настроенного на создание узла службы, который автоматически настраивает конечную точку AJAX.</span><span class="sxs-lookup"><span data-stu-id="362d5-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="362d5-110">Создание служб WCF AJAX без использования ASP.NET</span><span class="sxs-lookup"><span data-stu-id="362d5-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="362d5-111">Описывает, как создать службу WCF без использования ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="362d5-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="362d5-112">Поддержка JSON и других форматов передачи данных</span><span class="sxs-lookup"><span data-stu-id="362d5-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="362d5-113">Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX (вместо XML).</span><span class="sxs-lookup"><span data-stu-id="362d5-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="362d5-114">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="362d5-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="362d5-115">Описывает, как перейти на веб-службы WCF с поддержкой AJAX ASP.NET веб-службой.</span><span class="sxs-lookup"><span data-stu-id="362d5-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="362d5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="362d5-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="362d5-117">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="362d5-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
