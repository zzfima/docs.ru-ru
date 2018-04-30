---
title: Безопасные сеансы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 068615510d7e1d73ae260441ccef6536ee6ff317
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="secure-sessions"></a><span data-ttu-id="f65c1-102">Безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="f65c1-102">Secure Sessions</span></span>
<span data-ttu-id="f65c1-103">Безопасные сеансы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] обеспечивают получение сообщений в порядке их отправки.</span><span class="sxs-lookup"><span data-stu-id="f65c1-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="f65c1-104">В этом разделе рассматриваются проблемы безопасности, которые необходимо учитывать при создании надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f65c1-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="f65c1-105">Дополнительные сведения о надежных сеансов см. в разделе [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="f65c1-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f65c1-106">Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера контекста безопасности с отслеживанием состояния (SCT).</span><span class="sxs-lookup"><span data-stu-id="f65c1-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="f65c1-107">При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="f65c1-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="f65c1-108">Дополнительные сведения см. в разделе [неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="f65c1-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f65c1-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f65c1-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="f65c1-110">Безопасные диалоги и безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="f65c1-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="f65c1-111">Безопасные диалоги и безопасные сеансы - это синонимы.</span><span class="sxs-lookup"><span data-stu-id="f65c1-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="f65c1-112">В этом разделе рассматривается, как работает безопасный диалог, а также когда и почему следует использовать шаблон.</span><span class="sxs-lookup"><span data-stu-id="f65c1-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="f65c1-113">Практическое руководство. Создание сеанса безопасности</span><span class="sxs-lookup"><span data-stu-id="f65c1-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="f65c1-114">Пошаговое руководство по основным этапам создания безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f65c1-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="f65c1-115">Практическое руководство. Создание маркера контекста безопасности с отслеживанием состояния для безопасного сеанса</span><span class="sxs-lookup"><span data-stu-id="f65c1-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="f65c1-116">Пошаговое руководство по созданию веб-фермы, которая будет поддерживать состояние и сеансы с клиентами.</span><span class="sxs-lookup"><span data-stu-id="f65c1-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="f65c1-117">Соображения о защите безопасных сеансов</span><span class="sxs-lookup"><span data-stu-id="f65c1-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="f65c1-118">Описание некоторых особенностей безопасных сеансов.</span><span class="sxs-lookup"><span data-stu-id="f65c1-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="f65c1-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f65c1-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="f65c1-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f65c1-120">Related Sections</span></span>  
 [<span data-ttu-id="f65c1-121">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="f65c1-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="f65c1-122">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="f65c1-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="f65c1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f65c1-123">See Also</span></span>  
 [<span data-ttu-id="f65c1-124">Практическое руководство. Включение обнаружения повтора сообщений</span><span class="sxs-lookup"><span data-stu-id="f65c1-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [<span data-ttu-id="f65c1-125">Атаки с повторением</span><span class="sxs-lookup"><span data-stu-id="f65c1-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [<span data-ttu-id="f65c1-126">Практическое руководство. Создание службы, для которой требуются сеансы</span><span class="sxs-lookup"><span data-stu-id="f65c1-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
