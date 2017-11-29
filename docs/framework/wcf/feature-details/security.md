---
title: "Безопасность Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
caps.latest.revision: "21"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 38f62a6ccc0c9291f3963173475f99d5800feb39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="0ed27-102">Безопасность Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="0ed27-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="0ed27-103">В подразделах этого раздела описываются средства безопасности [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и способы их использования для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="0ed27-103">The topics in this section describe [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security features and how to use them to help secure messages.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0ed27-104">Windows Server AppFabric и безопасности, в разделе [безопасности модели для Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="0ed27-104"> Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ed27-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="0ed27-105">In This Section</span></span>  
 [<span data-ttu-id="0ed27-106">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="0ed27-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="0ed27-107">Описание средств безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ed27-107">Describes the security features in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="0ed27-108">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="0ed27-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="0ed27-109">Основная терминология и основные понятия, связанные с функциями безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ed27-109">Describes the basic terminology and concepts used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security.</span></span>  
  
 [<span data-ttu-id="0ed27-110">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="0ed27-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="0ed27-111">Описание сценариев и топологий, конфигурируемых в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ed27-111">Describes scenarios and topologies you can configure with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="0ed27-112">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="0ed27-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="0ed27-113">Общие сведения о поведении WCF, которые оказывают влияние на безопасность, например на настройки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0ed27-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="0ed27-114">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="0ed27-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="0ed27-115">Описание привязок с точки зрения безопасности, в том числе демонстрация создания настраиваемых привязок безопасности.</span><span class="sxs-lookup"><span data-stu-id="0ed27-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="0ed27-116">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0ed27-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="0ed27-117">Принципы защиты сообщений с помощью функций безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ed27-117">Describes how to secure messages using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security features.</span></span>  
  
 [<span data-ttu-id="0ed27-118">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="0ed27-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="0ed27-119">Примеры типичных задач, связанных с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="0ed27-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="0ed27-120">Авторизация</span><span class="sxs-lookup"><span data-stu-id="0ed27-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="0ed27-121">Типичные сценарии авторизации с реализацией системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="0ed27-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="0ed27-122">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="0ed27-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="0ed27-123">Основы федерации и принципы создания клиентов, взаимодействующих с федеративными серверами.</span><span class="sxs-lookup"><span data-stu-id="0ed27-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="0ed27-124">Частичное доверие</span><span class="sxs-lookup"><span data-stu-id="0ed27-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="0ed27-125">Принципы выполнения сценариев с частичным доверием и ограничения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при выполнении с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="0ed27-125">Describes how to run partially-trusted scenarios and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="0ed27-126">Аудит</span><span class="sxs-lookup"><span data-stu-id="0ed27-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="0ed27-127">Принципы аудита событий безопасности.</span><span class="sxs-lookup"><span data-stu-id="0ed27-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="0ed27-128">Рекомендации по обеспечению безопасности и рекомендации</span><span class="sxs-lookup"><span data-stu-id="0ed27-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="0ed27-129">Рекомендации по созданию защищенных приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ed27-129">Guidelines for creating secure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0ed27-130">Ссылка</span><span class="sxs-lookup"><span data-stu-id="0ed27-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="0ed27-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0ed27-131">Related Sections</span></span>  
 [<span data-ttu-id="0ed27-132">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="0ed27-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="0ed27-133">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="0ed27-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="0ed27-134">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="0ed27-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="0ed27-135">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="0ed27-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ed27-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0ed27-136">See Also</span></span>  
 [<span data-ttu-id="0ed27-137">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="0ed27-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
