---
title: Подробные сведения о возможностях WCF
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
- features [WCF]
- WCF, features
- Windows Communication Foundation, features
ms.assetid: 9b4368ca-0bd3-40dc-a539-bcd5779cee5f
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2aa8adc0ce197c3776b8314009fcaa061bed884d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-feature-details"></a><span data-ttu-id="806ac-102">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="806ac-102">WCF Feature Details</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="806ac-103"> обеспечивает всеобъемлющий контроль функций отправки сообщений приложения.</span><span class="sxs-lookup"><span data-stu-id="806ac-103"> allows extensive control over the messaging functions of an application.</span></span> <span data-ttu-id="806ac-104">В подразделах этого раздела подробно описываются имеющиеся возможности.</span><span class="sxs-lookup"><span data-stu-id="806ac-104">The topics in this section go into detail about the available features.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="806ac-105">Основные программирования, см. в разделе [базовое Программирование WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="806ac-105"> basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="806ac-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="806ac-106">In This Section</span></span>  
 [<span data-ttu-id="806ac-107">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="806ac-107">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 <span data-ttu-id="806ac-108">Описывает создание и настройку служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="806ac-108">Describes how to create and configure workflow services.</span></span>  
  
 [<span data-ttu-id="806ac-109">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="806ac-109">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 <span data-ttu-id="806ac-110">Описывает способ контроля нескольких аспектов службы.</span><span class="sxs-lookup"><span data-stu-id="806ac-110">Describes how to control multiple aspects of your service.</span></span>  
  
 [<span data-ttu-id="806ac-111">Передача данных и сериализация</span><span class="sxs-lookup"><span data-stu-id="806ac-111">Data Transfer and Serialization</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)  
 <span data-ttu-id="806ac-112">Описывает способ настройки сериализации данных для совместной работы или будущей совместимости.</span><span class="sxs-lookup"><span data-stu-id="806ac-112">Describes how serialization of data can be tailored for interoperation or future compatibility.</span></span>  
  
 [<span data-ttu-id="806ac-113">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="806ac-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 <span data-ttu-id="806ac-114">Описывает создание экземпляров и режимов сеанса [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и способ выбора правильного режима для приложения.</span><span class="sxs-lookup"><span data-stu-id="806ac-114">Describes the instancing and session modes of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and how to select the right mode for your application.</span></span>  
  
 [<span data-ttu-id="806ac-115">Транспорты</span><span class="sxs-lookup"><span data-stu-id="806ac-115">Transports</span></span>](../../../../docs/framework/wcf/feature-details/transports.md)  
 <span data-ttu-id="806ac-116">Описывает способ настройки транспортного уровня, нижнего уровня стека каналов.</span><span class="sxs-lookup"><span data-stu-id="806ac-116">Describes how to configure the transport layer, the lowest level of the channel stack.</span></span>  
  
 [<span data-ttu-id="806ac-117">Очереди и надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="806ac-117">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)  
 <span data-ttu-id="806ac-118">Описывает очереди, хранящие сообщения отправляющего приложения от имени получающего приложения и позднее перенаправляющие эти сообщения получающему приложению.</span><span class="sxs-lookup"><span data-stu-id="806ac-118">Describes queues, which store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span>  
  
 [<span data-ttu-id="806ac-119">Транзакции</span><span class="sxs-lookup"><span data-stu-id="806ac-119">Transactions</span></span>](../../../../docs/framework/wcf/feature-details/transactions-in-wcf.md)  
 <span data-ttu-id="806ac-120">Объясняет, как создать транзакционные операции с возможностью отката при необходимости.</span><span class="sxs-lookup"><span data-stu-id="806ac-120">Explains how to create transacted operations that can be rolled back if needed.</span></span>  
  
 [<span data-ttu-id="806ac-121">Безопасность</span><span class="sxs-lookup"><span data-stu-id="806ac-121">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 <span data-ttu-id="806ac-122">Описывает, как безопасность [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] помогает создавать приложения с конфиденциальностью и целостностью.</span><span class="sxs-lookup"><span data-stu-id="806ac-122">Describes how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security helps you to create applications that have confidentiality and integrity.</span></span> <span data-ttu-id="806ac-123">Кроме того, в качестве возможностей аудита имеются проверка подлинности и авторизация.</span><span class="sxs-lookup"><span data-stu-id="806ac-123">Authentication and authorization are also available, as are auditing features.</span></span>  
  
 [<span data-ttu-id="806ac-124">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="806ac-124">Peer-to-Peer Networking</span></span>](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 <span data-ttu-id="806ac-125">Подробная информация о способе создания одноранговых служб и клиентов.</span><span class="sxs-lookup"><span data-stu-id="806ac-125">Details how to create peer services and clients.</span></span>  
  
 [<span data-ttu-id="806ac-126">Метаданные</span><span class="sxs-lookup"><span data-stu-id="806ac-126">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 <span data-ttu-id="806ac-127">Описывает архитектуру и форматы метаданных.</span><span class="sxs-lookup"><span data-stu-id="806ac-127">Describes metadata architecture and formats.</span></span>  
  
 [<span data-ttu-id="806ac-128">Клиенты</span><span class="sxs-lookup"><span data-stu-id="806ac-128">Clients</span></span>](../../../../docs/framework/wcf/feature-details/clients.md)  
 <span data-ttu-id="806ac-129">Описывает способ создания различных клиентов для доступа к службам.</span><span class="sxs-lookup"><span data-stu-id="806ac-129">Describes how to create a variety of clients that access services.</span></span>  
  
 [<span data-ttu-id="806ac-130">Размещение</span><span class="sxs-lookup"><span data-stu-id="806ac-130">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 <span data-ttu-id="806ac-131">Описывает размещение.</span><span class="sxs-lookup"><span data-stu-id="806ac-131">Describes hosting.</span></span> <span data-ttu-id="806ac-132">Служба может размещаться в другом приложении или быть резидентной (размещаться сама в себе).</span><span class="sxs-lookup"><span data-stu-id="806ac-132">A service can be hosted by another application, or it can be self-hosted.</span></span>  
  
 [<span data-ttu-id="806ac-133">Взаимодействие и интеграция</span><span class="sxs-lookup"><span data-stu-id="806ac-133">Interoperability and Integration</span></span>](../../../../docs/framework/wcf/feature-details/interoperability-and-integration.md)  
 <span data-ttu-id="806ac-134">Описывает использование [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для расширения существующей логики вместо ее переписывания при существенном изменении логики компонентно-ориентированного приложения, размещенного в COM+.</span><span class="sxs-lookup"><span data-stu-id="806ac-134">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to extend your existing logic rather than having to rewrite it if you have a substantial investment in component-based application logic hosted in COM+.</span></span>  
  
 [<span data-ttu-id="806ac-135">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="806ac-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 <span data-ttu-id="806ac-136">Описывает модель веб-программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], позволяющую разработчикам предоставлять операции службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] конечным точкам, не являющимся конечными точками SOAP.</span><span class="sxs-lookup"><span data-stu-id="806ac-136">Describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Programming Model that allows developers to expose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service operations to non-SOAP endpoints.</span></span>  
  
 [<span data-ttu-id="806ac-137">Синдикация WCF</span><span class="sxs-lookup"><span data-stu-id="806ac-137">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)  
 <span data-ttu-id="806ac-138">Описывает поддержку простого экспонирования веб-каналов синдикации из службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="806ac-138">Describes support to easily expose syndication feeds from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [<span data-ttu-id="806ac-139">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="806ac-139">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 <span data-ttu-id="806ac-140">Описывает поддержку форматов данных асинхронных сценариев JavaScript, XML (AJAX) и JSON в ASP.NET, позволяющую службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставлять операции клиентам AJAX.</span><span class="sxs-lookup"><span data-stu-id="806ac-140">Describes support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format to allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span>  
  
 [<span data-ttu-id="806ac-141">Обнаружение WCF</span><span class="sxs-lookup"><span data-stu-id="806ac-141">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
 <span data-ttu-id="806ac-142">Описывает поддержку для включения обнаружения служб во время выполнения совместимым способом с помощью протокола WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="806ac-142">Describes support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span>  
  
 [<span data-ttu-id="806ac-143">Маршрутизация</span><span class="sxs-lookup"><span data-stu-id="806ac-143">Routing</span></span>](../../../../docs/framework/wcf/feature-details/routing.md)  
 <span data-ttu-id="806ac-144">Описывает службу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="806ac-144">Describes the routing service.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="806ac-145">Ссылка</span><span class="sxs-lookup"><span data-stu-id="806ac-145">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.ServiceModel.Routing>  
  
## <a name="related-sections"></a><span data-ttu-id="806ac-146">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="806ac-146">Related Sections</span></span>  
 [<span data-ttu-id="806ac-147">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="806ac-147">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
