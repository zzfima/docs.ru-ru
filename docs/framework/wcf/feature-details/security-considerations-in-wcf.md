---
title: Вопросы безопасности в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 6cc19f7719b9cdbcd3852c99f450c1d728dc833b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746001"
---
# <a name="security-considerations-in-wcf"></a><span data-ttu-id="eddab-102">Вопросы безопасности в WCF</span><span class="sxs-lookup"><span data-stu-id="eddab-102">Security Considerations in WCF</span></span>
<span data-ttu-id="eddab-103">В подразделах в этом разделе перечислены различные элементы, связанные с безопасностью, которые следует учитывать при разработке приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eddab-103">The topics in this section list various security-related items to consider when designing a Windows Communication Foundation (WCF) application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eddab-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="eddab-104">In This Section</span></span>  
 [<span data-ttu-id="eddab-105">Раскрытие информации</span><span class="sxs-lookup"><span data-stu-id="eddab-105">Information Disclosure</span></span>](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 <span data-ttu-id="eddab-106">Описание различных способов раскрытия информации и атак, а также способов их предотвращения.</span><span class="sxs-lookup"><span data-stu-id="eddab-106">Discusses the various ways that information can be disclosed or attacked, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="eddab-107">Повышение привилегий</span><span class="sxs-lookup"><span data-stu-id="eddab-107">Elevation of Privilege</span></span>](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 <span data-ttu-id="eddab-108">Описание последствий предоставления злоумышленнику более широких прав по сравнению с правами, предоставленными ему изначально, и способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="eddab-108">Discusses the effects of giving an attacker authorization permissions beyond those initially granted and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="eddab-109">Отказ в обслуживании</span><span class="sxs-lookup"><span data-stu-id="eddab-109">Denial of Service</span></span>](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 <span data-ttu-id="eddab-110">Описание ситуаций, когда система не может обрабатывать сообщения должным образом, и способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="eddab-110">Discusses what happens when a system is unable to process messages appropriately and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="eddab-111">Подделка</span><span class="sxs-lookup"><span data-stu-id="eddab-111">Tampering</span></span>](../../../../docs/framework/wcf/feature-details/tampering.md)  
 <span data-ttu-id="eddab-112">Описание изменения сообщений или доставки сообщений, а также способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="eddab-112">Discusses the altering of messages or the delivery of messages and how to mitigate it.</span></span>  
  
 [<span data-ttu-id="eddab-113">Атаки с повторением</span><span class="sxs-lookup"><span data-stu-id="eddab-113">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 <span data-ttu-id="eddab-114">Описание последствий копирования злоумышленником потока сообщений между двумя сторонами и воспроизведения этого потока для одной или нескольких сторон, а также способов решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="eddab-114">Discusses what happens when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties, and how to mitigate this.</span></span>  
  
 [<span data-ttu-id="eddab-115">Соображения о защите безопасных сеансов</span><span class="sxs-lookup"><span data-stu-id="eddab-115">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 <span data-ttu-id="eddab-116">Описание следующих элементов, влияющих на безопасность при реализации безопасных сеансов.</span><span class="sxs-lookup"><span data-stu-id="eddab-116">Discusses the following items that affect security when implementing secure sessions.</span></span>  
  
 [<span data-ttu-id="eddab-117">Неподдерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="eddab-117">Unsupported Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 <span data-ttu-id="eddab-118">Перечисление различных сценариев, которые не поддерживают определенный аспект безопасности, и которых следует избегать или учитывать.</span><span class="sxs-lookup"><span data-stu-id="eddab-118">Lists various scenarios that do not support a particular aspect of security and should be avoided or considered.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eddab-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="eddab-119">Reference</span></span>  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="eddab-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="eddab-120">Related Sections</span></span>  
 [<span data-ttu-id="eddab-121">Руководство и рекомендации по безопасности</span><span class="sxs-lookup"><span data-stu-id="eddab-121">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a><span data-ttu-id="eddab-122">См. также</span><span class="sxs-lookup"><span data-stu-id="eddab-122">See also</span></span>
- [<span data-ttu-id="eddab-123">Безопасность</span><span class="sxs-lookup"><span data-stu-id="eddab-123">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
