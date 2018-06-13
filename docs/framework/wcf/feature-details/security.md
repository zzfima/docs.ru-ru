---
title: Безопасность Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: fb48ae39d269f21a7120ecf143dc4c4680efe39d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499093"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="89a40-102">Безопасность Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="89a40-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="89a40-103">В этом разделе описываются средства безопасности Windows Communication Foundation (WCF) и способ их использования для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="89a40-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="89a40-104">Дополнительные сведения о Windows Server AppFabric и безопасности см. в разделе [безопасности модели для Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="89a40-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89a40-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="89a40-105">In This Section</span></span>  
 [<span data-ttu-id="89a40-106">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="89a40-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="89a40-107">Описывает средства безопасности в WCF.</span><span class="sxs-lookup"><span data-stu-id="89a40-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="89a40-108">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="89a40-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="89a40-109">Описывает основные термины и понятия, используемые в системе безопасности WCF.</span><span class="sxs-lookup"><span data-stu-id="89a40-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="89a40-110">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="89a40-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="89a40-111">Описание сценариев и топологий, которые можно настроить с помощью WCF.</span><span class="sxs-lookup"><span data-stu-id="89a40-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="89a40-112">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="89a40-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="89a40-113">Общие сведения о поведении WCF, которые оказывают влияние на безопасность, например на настройки учетных данных.</span><span class="sxs-lookup"><span data-stu-id="89a40-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="89a40-114">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="89a40-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="89a40-115">Описание привязок с точки зрения безопасности, в том числе демонстрация создания настраиваемых привязок безопасности.</span><span class="sxs-lookup"><span data-stu-id="89a40-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="89a40-116">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="89a40-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="89a40-117">Описание способов защиты сообщений с помощью средств безопасности WCF.</span><span class="sxs-lookup"><span data-stu-id="89a40-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="89a40-118">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="89a40-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="89a40-119">Примеры типичных задач, связанных с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="89a40-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="89a40-120">Авторизация</span><span class="sxs-lookup"><span data-stu-id="89a40-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="89a40-121">Типичные сценарии авторизации с реализацией системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="89a40-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="89a40-122">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="89a40-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="89a40-123">Основы федерации и принципы создания клиентов, взаимодействующих с федеративными серверами.</span><span class="sxs-lookup"><span data-stu-id="89a40-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="89a40-124">Частичное доверие</span><span class="sxs-lookup"><span data-stu-id="89a40-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="89a40-125">Описание способов выполнения сценариев с частичным доверием и ограничения WCF при выполнении с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="89a40-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="89a40-126">Аудит</span><span class="sxs-lookup"><span data-stu-id="89a40-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="89a40-127">Принципы аудита событий безопасности.</span><span class="sxs-lookup"><span data-stu-id="89a40-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="89a40-128">Руководство и рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="89a40-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="89a40-129">Рекомендации по созданию безопасных приложений WCF.</span><span class="sxs-lookup"><span data-stu-id="89a40-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="89a40-130">Ссылка</span><span class="sxs-lookup"><span data-stu-id="89a40-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="89a40-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="89a40-131">Related Sections</span></span>  
 [<span data-ttu-id="89a40-132">Подробные сведения о возможностях WCF</span><span class="sxs-lookup"><span data-stu-id="89a40-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="89a40-133">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="89a40-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="89a40-134">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="89a40-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="89a40-135">Концептуальный обзор</span><span class="sxs-lookup"><span data-stu-id="89a40-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="89a40-136">См. также</span><span class="sxs-lookup"><span data-stu-id="89a40-136">See Also</span></span>  
 [<span data-ttu-id="89a40-137">Настройка приложения</span><span class="sxs-lookup"><span data-stu-id="89a40-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
