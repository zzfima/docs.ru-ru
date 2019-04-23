---
title: Интеграция с AJAX и поддержка JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: a3d9c29f3223624653f2d568bb351d90334a4318
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137115"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="83097-102">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="83097-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="83097-103">Поддержка Windows Communication Foundation (WCF) для ASP.NET Asynchronous JavaScript and XML (AJAX) и формат данных JavaScript Object Notation (JSON) позволяют службам WCF предоставлять операции клиентам AJAX.</span><span class="sxs-lookup"><span data-stu-id="83097-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="83097-104">Клиенты AJAX представляют собой веб-страниц, в которых выполняется код JavaScript и доступа к этим службам WCF, с помощью HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="83097-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="83097-105">В этом разделе приведены сведения о такой поддержке и способах ее реализации.</span><span class="sxs-lookup"><span data-stu-id="83097-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="83097-106">Дополнительные сведения о ASP.NET AJAX и его интеграции с ASP.NET 2.0, см. в разделе [Общие сведения о ASP.NET AJAX](https://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="83097-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83097-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="83097-107">In This Section</span></span>  
 [<span data-ttu-id="83097-108">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="83097-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="83097-109">Описывает, как это служба WCF доступные клиентам AJAX, добавив соответствующую конечную точку AJAX, либо через конфигурацию или с помощью фабрики узла службы, настроенного на создание узла службы, который автоматически настраивает конечную точку AJAX.</span><span class="sxs-lookup"><span data-stu-id="83097-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="83097-110">Создание служб WCF AJAX без использования ASP.NET</span><span class="sxs-lookup"><span data-stu-id="83097-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="83097-111">В этой статье описывается создание службы WCF без использования ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="83097-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="83097-112">Поддержка JSON и других форматов передачи данных</span><span class="sxs-lookup"><span data-stu-id="83097-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="83097-113">Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX (вместо XML).</span><span class="sxs-lookup"><span data-stu-id="83097-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="83097-114">Практическое руководство. Миграция с поддержкой AJAX веб-служб ASP.NET в WCF</span><span class="sxs-lookup"><span data-stu-id="83097-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="83097-115">В этой статье описывается миграция службы веб-служб с поддержкой AJAX ASP.NET в WCF веб-службы.</span><span class="sxs-lookup"><span data-stu-id="83097-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83097-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83097-116">See also</span></span>

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="83097-117">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="83097-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
