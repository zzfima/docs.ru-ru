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
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679138"
---
# <a name="reliable-sessions"></a><span data-ttu-id="8deaa-102">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="8deaa-102">Reliable Sessions</span></span>

<span data-ttu-id="8deaa-103">В этом разделе описывается, какие Windows Communication Foundation (WCF) надежный сеанс, чего он используется, как и когда им воспользоваться, какие конфигурации привязки поддерживают его, и ссылки на рекомендации.</span><span class="sxs-lookup"><span data-stu-id="8deaa-103">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="8deaa-104">В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.</span><span class="sxs-lookup"><span data-stu-id="8deaa-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="8deaa-105">Надежные сеансы WCF предоставляет функции, то, что сообщения, которыми обмениваются конечные точки, передаются по SOAP или через транспортных посредников и доставляются только один раз и, возможно, в том же порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="8deaa-105">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="8deaa-106">Чтобы использовать надежные сеансы с приложения WCF, используйте один из предоставляемых системой привязок в WCF, которые поддерживают надежные сеансы, по умолчанию или в качестве параметра или создать собственную пользовательскую привязку, которая поддерживает сеанс.</span><span class="sxs-lookup"><span data-stu-id="8deaa-106">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8deaa-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8deaa-107">In This Section</span></span>

<span data-ttu-id="8deaa-108">[Общие сведения о надежных сеансах](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) описание надежных сеансов, когда следует использовать их, различных привязок, которые поддерживают надежные сеансы, и как они работают.</span><span class="sxs-lookup"><span data-stu-id="8deaa-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="8deaa-109">[Практическое руководство. Exchange сообщения в рамках надежного сеанса](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) описывается, как создать надежный сеанс по протоколу HTTP с помощью пользовательской привязки, заданной в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8deaa-109">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="8deaa-110">[Практическое руководство. Защита сообщений с помощью надежных сеансов](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) описываются способы защиты надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8deaa-110">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="8deaa-111">[Практическое руководство. Создать привязку Custom надежного сеанса с помощью протокола HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) описывается, как создать надежный сеанс по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8deaa-111">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="8deaa-112">[Советы и рекомендации для надежных сеансов](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) описывает некоторые рекомендации, связанные с использованием надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8deaa-112">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="8deaa-113">Ссылка</span><span class="sxs-lookup"><span data-stu-id="8deaa-113">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="8deaa-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8deaa-114">See also</span></span>

- [<span data-ttu-id="8deaa-115">Очереди и надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="8deaa-115">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [<span data-ttu-id="8deaa-116">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="8deaa-116">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
