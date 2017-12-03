---
title: "Надежные сеансы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53bb63fbbcf92650085514118a5e9464ab2dea30
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-sessions"></a><span data-ttu-id="6704f-102">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="6704f-102">Reliable Sessions</span></span>

<span data-ttu-id="6704f-103">В этом разделе рассказывается, что [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] надежного сеанса является то, что он используется, как и когда следует использовать, какие конфигурации привязки поддерживают его, а также приведены ссылки на рекомендации.</span><span class="sxs-lookup"><span data-stu-id="6704f-103">This section describes what a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="6704f-104">В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.</span><span class="sxs-lookup"><span data-stu-id="6704f-104">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="6704f-105">Надежный сеанс [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет функциям поддержки передаются через посредников SOAP и транспорта сообщений, пересылаемых между конечными точками и доставляются только один раз и, возможно, в том же порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="6704f-105">The reliable session [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides featrues ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="6704f-106">Для применения надежных сеансов в приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] следует использовать предоставляемые системой привязки в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которые по умолчанию поддерживают надежные сеансы, либо можно создать собственную пользовательскую привязку, которая бы поддерживала такие сеансы.</span><span class="sxs-lookup"><span data-stu-id="6704f-106">To use a reliable session with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, either use one of the system-provided bindings in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6704f-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="6704f-107">In This Section</span></span>

<span data-ttu-id="6704f-108">[Общие сведения о надежных сеансов](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="6704f-108">[Reliable Sessions Overview](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) </span></span>  
<span data-ttu-id="6704f-109">Описание надежных сеансов, ситуаций, в которых они используются, различных привязок, которые поддерживают надежные сеансы, и принципы их работы.</span><span class="sxs-lookup"><span data-stu-id="6704f-109">Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="6704f-110">[Как: обмена сообщениями в ходе надежного сеанса](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span><span class="sxs-lookup"><span data-stu-id="6704f-110">[How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) </span></span>  
<span data-ttu-id="6704f-111">Описание процесса создания надежного сеанса через протокол HTTP с помощью пользовательской привязки, заданной в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6704f-111">Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="6704f-112">[Как: защита сообщений с помощью надежных сеансов](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="6704f-112">[How to: Secure Messages within Reliable Sessions](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) </span></span>  
<span data-ttu-id="6704f-113">Обеспечение защиты надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="6704f-113">Describes how to secure a reliable session.</span></span>

<span data-ttu-id="6704f-114">[Как: Создание пользовательской привязки надежного сеанса с использованием HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span><span class="sxs-lookup"><span data-stu-id="6704f-114">[How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) </span></span>  
<span data-ttu-id="6704f-115">Создание надежного сеанса через протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6704f-115">Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="6704f-116">[Советы и рекомендации для надежных сеансов](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="6704f-116">[Best Practices for Reliable Sessions](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) </span></span>  
<span data-ttu-id="6704f-117">Описание некоторых рекомендаций по использованию надежных сеансов.</span><span class="sxs-lookup"><span data-stu-id="6704f-117">Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="6704f-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6704f-118">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="6704f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6704f-119">See Also</span></span>

<span data-ttu-id="6704f-120">[Очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="6704f-120">[Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md) </span></span>  
[<span data-ttu-id="6704f-121">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="6704f-121">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
