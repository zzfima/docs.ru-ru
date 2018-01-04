---
title: "Вопросы безопасности в WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
caps.latest.revision: "49"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f35bd56bdc69f8c57a7e46984778051b57b7a06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="b6c81-102">Вопросы безопасности в WCF</span><span class="sxs-lookup"><span data-stu-id="b6c81-102">Security Considerations in WCF</span></span>
<span data-ttu-id="b6c81-103">В подразделах этого раздела перечислены различные пункты, связанные с безопасностью, которые следует учитывать при разработке приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6c81-103">The topics in this section list various security-related items to consider when designing a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6c81-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b6c81-104">In This Section</span></span>  
 [<span data-ttu-id="b6c81-105">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="b6c81-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="b6c81-106">Описание различных способов раскрытия информации и атак, а также способов их предотвращения.</span><span class="sxs-lookup"><span data-stu-id="b6c81-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="b6c81-107">Повышение привилегий</span><span class="sxs-lookup"><span data-stu-id="b6c81-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="b6c81-108">Описание последствий предоставления злоумышленнику более широких прав по сравнению с правами, предоставленными ему изначально, и способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="b6c81-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="b6c81-109">Отказ в обслуживании</span><span class="sxs-lookup"><span data-stu-id="b6c81-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="b6c81-110">Описание ситуаций, когда система не может обрабатывать сообщения должным образом, и способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="b6c81-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="b6c81-111">Подделка</span><span class="sxs-lookup"><span data-stu-id="b6c81-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="b6c81-112">Описание изменения сообщений или доставки сообщений, а также способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="b6c81-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="b6c81-113">Атаки с повторением</span><span class="sxs-lookup"><span data-stu-id="b6c81-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="b6c81-114">Описание последствий копирования злоумышленником потока сообщений между двумя сторонами и воспроизведения этого потока для одной или нескольких сторон, а также способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="b6c81-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="b6c81-115">Соображения о защите безопасных сеансов</span><span class="sxs-lookup"><span data-stu-id="b6c81-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="b6c81-116">Описание следующих элементов, влияющих на безопасность при реализации безопасных сеансов.</span><span class="sxs-lookup"><span data-stu-id="b6c81-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="b6c81-117">Неподдерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="b6c81-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="b6c81-118">Перечисление различных сценариев, которые не поддерживают определенный аспект безопасности, и которых следует избегать или учитывать.</span><span class="sxs-lookup"><span data-stu-id="b6c81-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b6c81-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="b6c81-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="b6c81-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b6c81-120">Related Sections</span></span>  
 [<span data-ttu-id="b6c81-121">Руководство и рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="b6c81-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="b6c81-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b6c81-122">See Also</span></span>  
 [<span data-ttu-id="b6c81-123">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b6c81-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
