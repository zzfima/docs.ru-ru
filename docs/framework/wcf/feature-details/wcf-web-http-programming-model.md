---
title: "Модель веб-программирования HTTP WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- web services programming model [WCF]
- POX
- REST
ms.assetid: 2312a8d3-b66e-4623-ba42-978434300c7f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32e7cb3a340865530b6a8d76609eb246184363b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-web-http-programming-model"></a><span data-ttu-id="03389-102">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="03389-102">WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="03389-103">Модель веб-программирования HTTP [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет разработчикам обрабатывать операции службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для конечных точек, не являющихся конечными точками SOAP.</span><span class="sxs-lookup"><span data-stu-id="03389-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model allows developers to expose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service operations to non-SOAP endpoints.</span></span> <span data-ttu-id="03389-104">Эта возможность подробно описана в следующих подразделах.</span><span class="sxs-lookup"><span data-stu-id="03389-104">The topics in this section examine the feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03389-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="03389-105">In This Section</span></span>  
 [<span data-ttu-id="03389-106">Общие сведения о модели программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="03389-106">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 <span data-ttu-id="03389-107">Содержит общие сведения о модели веб-программирования HTTP [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03389-107">Provides an overview of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model.</span></span>  
  
 [<span data-ttu-id="03389-108">Объектная модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="03389-108">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 <span data-ttu-id="03389-109">Описывает модель веб-программирования HTTP [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и принципы ее работы.</span><span class="sxs-lookup"><span data-stu-id="03389-109">Discusses the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model and how it works.</span></span>  
  
 [<span data-ttu-id="03389-110">Как: Создание веб-службы HTTP Basic WCF</span><span class="sxs-lookup"><span data-stu-id="03389-110">How to: Create a Basic WCF Web HTTP Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
 <span data-ttu-id="03389-111">Порядок написания простой службы, предоставляющей конечную точку, не являющуюся конечной точкой SOAP.</span><span class="sxs-lookup"><span data-stu-id="03389-111">Describes how to write a basic service that exposes a non-SOAP endpoint.</span></span>  
  
 [<span data-ttu-id="03389-112">Как: предоставление контрактов SOAP и веб-клиентов</span><span class="sxs-lookup"><span data-stu-id="03389-112">How to: Expose a Contract to SOAP and Web Clients</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md)  
 <span data-ttu-id="03389-113">Порядок написания простой службы, предоставляющей один и тот же контракт клиентам SOAP и клиентам, не работающим по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="03389-113">Describes how to write a basic service that exposes the same contract to both SOAP and non-SOAP clients.</span></span>  
  
 [<span data-ttu-id="03389-114">UriTemplate и UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="03389-114">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 <span data-ttu-id="03389-115">Описание управления универсальными кодами ресурсов (URI) с помощью классов <xref:System.UriTemplate> и <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="03389-115">Describes how to control URIs using <xref:System.UriTemplate> and <xref:System.UriTemplateTable>.</span></span>  
  
 [<span data-ttu-id="03389-116">Поддержка кэширования для веб-службы HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="03389-116">Caching Support for WCF Web HTTP Services</span></span>](../../../../docs/framework/wcf/feature-details/caching-support-for-wcf-web-http-services.md)  
 <span data-ttu-id="03389-117">Описывает, как указать порядок кэширования для веб-службы HTTP WCF.</span><span class="sxs-lookup"><span data-stu-id="03389-117">Describes how to specify caching behavior for a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="03389-118">Форматирование WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="03389-118">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 <span data-ttu-id="03389-119">Описывает, как указать формат ответа от веб-службы HTTP WCF.</span><span class="sxs-lookup"><span data-stu-id="03389-119">Describes how to specify the format of the response from a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="03389-120">Обработка ошибок HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="03389-120">WCF Web HTTP Error Handling</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-error-handling.md)  
 <span data-ttu-id="03389-121">Описывает, как возвращать ошибки веб-клиентам WCF, включающие коды состояния HTTP и дополнительные, определяемые пользователями данные ошибок.</span><span class="sxs-lookup"><span data-stu-id="03389-121">Describes how to return errors to WCF Web clients including HTTP status codes and additional user-defined error data.</span></span>  
  
 [<span data-ttu-id="03389-122">Вызов REST-службы из службы WCF</span><span class="sxs-lookup"><span data-stu-id="03389-122">Calling a REST-style service from a WCF service</span></span>](../../../../docs/framework/wcf/feature-details/calling-a-rest-style-service-from-a-wcf-service.md)  
 <span data-ttu-id="03389-123">Описывает, как вызвать REST-службу из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="03389-123">Describes how to call a REST-style service from inside a WCF service.</span></span>
