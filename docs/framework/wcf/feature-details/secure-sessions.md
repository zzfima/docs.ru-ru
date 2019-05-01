---
title: Безопасные сеансы
ms.date: 03/30/2017
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
ms.openlocfilehash: 8f5cf9a965951bcc1049c2e96ae6cfa80b0113ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990981"
---
# <a name="secure-sessions"></a><span data-ttu-id="a3990-102">Безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="a3990-102">Secure Sessions</span></span>
<span data-ttu-id="a3990-103">Функция Windows Communication Foundation (WCF) — надежные сеансы, которые гарантируют, что сообщения получаются в порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="a3990-103">A feature of Windows Communication Foundation (WCF) is reliable sessions that guarantee messages are received in the order they were sent.</span></span> <span data-ttu-id="a3990-104">В этом разделе рассматриваются проблемы безопасности, которые необходимо учитывать при создании надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="a3990-104">The topics in this section discuss the security implications to consider when creating a reliable session.</span></span> <span data-ttu-id="a3990-105">Дополнительные сведения о надежных сеансах см. в разделе [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="a3990-105">For more information about reliable sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3990-106">Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера контекста безопасности с отслеживанием состояния (SCT).</span><span class="sxs-lookup"><span data-stu-id="a3990-106">When impersonation is required on Windows XP, use a secure session without a stateful security context token (SCT).</span></span> <span data-ttu-id="a3990-107">При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="a3990-107">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="a3990-108">Дополнительные сведения см. в разделе [неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="a3990-108">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3990-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a3990-109">In This Section</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="a3990-110">Безопасные диалоги и безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="a3990-110">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|<span data-ttu-id="a3990-111">Безопасные диалоги и безопасные сеансы - это синонимы.</span><span class="sxs-lookup"><span data-stu-id="a3990-111">Secure conversations and secure sessions are synonymous.</span></span> <span data-ttu-id="a3990-112">В этом разделе рассматривается, как работает безопасный диалог, а также когда и почему следует использовать шаблон.</span><span class="sxs-lookup"><span data-stu-id="a3990-112">This topic explains the way a secure conversation works, and when and why to use the pattern.</span></span>|  
|[<span data-ttu-id="a3990-113">Практическое руководство. Создание сеанса безопасности</span><span class="sxs-lookup"><span data-stu-id="a3990-113">How to: Create a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|<span data-ttu-id="a3990-114">Пошаговое руководство по основным этапам создания безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="a3990-114">Walks through of the basics of creating a secure session.</span></span>|  
|[<span data-ttu-id="a3990-115">Практическое руководство. Создайте контекст безопасности маркера для безопасного сеанса</span><span class="sxs-lookup"><span data-stu-id="a3990-115">How to: Create a Security Context Token for a Secure Session</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|<span data-ttu-id="a3990-116">Пошаговое руководство по созданию веб-фермы, которая будет поддерживать состояние и сеансы с клиентами.</span><span class="sxs-lookup"><span data-stu-id="a3990-116">Walks through the steps of creating a Web farm that will maintain state and sessions with clients.</span></span>|  
|[<span data-ttu-id="a3990-117">Соображения о защите безопасных сеансов</span><span class="sxs-lookup"><span data-stu-id="a3990-117">Security Considerations for Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|<span data-ttu-id="a3990-118">Описание некоторых особенностей безопасных сеансов.</span><span class="sxs-lookup"><span data-stu-id="a3990-118">Describes special considerations for secure sessions.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="a3990-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="a3990-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="a3990-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a3990-120">Related Sections</span></span>  
 [<span data-ttu-id="a3990-121">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="a3990-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [<span data-ttu-id="a3990-122">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="a3990-122">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="a3990-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a3990-123">See also</span></span>

- [<span data-ttu-id="a3990-124">Практическое руководство. Включение обнаружения повтора сообщений</span><span class="sxs-lookup"><span data-stu-id="a3990-124">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)
- [<span data-ttu-id="a3990-125">Атаки с повторением</span><span class="sxs-lookup"><span data-stu-id="a3990-125">Replay Attacks</span></span>](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [<span data-ttu-id="a3990-126">Практическое руководство. Создание службы, которой требуются сеансы</span><span class="sxs-lookup"><span data-stu-id="a3990-126">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
