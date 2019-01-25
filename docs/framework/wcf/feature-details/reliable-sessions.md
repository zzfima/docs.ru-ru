---
title: Надежные сеансы
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735429"
---
# <a name="reliable-sessions"></a><span data-ttu-id="99acf-102">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="99acf-102">Reliable Sessions</span></span>

<span data-ttu-id="99acf-103">В этом разделе описывается, какие Windows Communication Foundation (WCF) надежный сеанс, чего он используется, как и когда им воспользоваться, какие конфигурации привязки поддерживают его, и ссылки на рекомендации.</span><span class="sxs-lookup"><span data-stu-id="99acf-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="99acf-104">В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.</span><span class="sxs-lookup"><span data-stu-id="99acf-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="99acf-105">Надежные сеансы WCF предоставляет функциям, то, что сообщения, которыми обмениваются конечные точки, передаются по SOAP или через транспортных посредников и доставляются только один раз и, возможно, в том же порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="99acf-105">The reliable session WCF provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="99acf-106">Чтобы использовать надежные сеансы с приложения WCF, используйте один из предоставляемых системой привязок в WCF, которые поддерживают надежные сеансы, по умолчанию или в качестве параметра или создать собственную пользовательскую привязку, которая поддерживает сеанс.</span><span class="sxs-lookup"><span data-stu-id="99acf-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="99acf-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="99acf-107">In This Section</span></span>

<span data-ttu-id="99acf-108">[Общие сведения о надежных сеансах](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="99acf-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="99acf-109">Описание надежных сеансов, ситуаций, в которых они используются, различных привязок, которые поддерживают надежные сеансы, и принципы их работы.</span><span class="sxs-lookup"><span data-stu-id="99acf-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="99acf-110">[Практическое руководство. Обмен сообщениями в рамках надежного сеанса](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="99acf-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="99acf-111">Описание процесса создания надежного сеанса через протокол HTTP с помощью пользовательской привязки, заданной в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99acf-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="99acf-112">[Практическое руководство. Защита сообщений с помощью надежных сеансов](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="99acf-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="99acf-113">Обеспечение защиты надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="99acf-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="99acf-114">[Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="99acf-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="99acf-115">Создание надежного сеанса через протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="99acf-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="99acf-116">[Советы и рекомендации для надежных сеансов](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="99acf-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="99acf-117">Описание некоторых рекомендаций по использованию надежных сеансов.</span><span class="sxs-lookup"><span data-stu-id="99acf-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="99acf-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="99acf-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="99acf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="99acf-119">See also</span></span>

- [<span data-ttu-id="99acf-120">Очереди и надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="99acf-120">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="99acf-121">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="99acf-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
