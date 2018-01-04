---
title: "Безопасность транспорта"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 364326e2ded11f7174adc891a5fd9bcdd3c98334
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transport-security"></a><span data-ttu-id="6747b-102">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="6747b-102">Transport Security</span></span>
<span data-ttu-id="6747b-103">Безопасность транспорта в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] зависит от выбранной привязки.</span><span class="sxs-lookup"><span data-stu-id="6747b-103">Transport security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] depends on the binding selected.</span></span> <span data-ttu-id="6747b-104">Транспорт, реализуемый привязкой, определяет фактический механизм безопасности.</span><span class="sxs-lookup"><span data-stu-id="6747b-104">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="6747b-105">В подразделах данного раздела описываются реализуемые механизмы и их параметры.</span><span class="sxs-lookup"><span data-stu-id="6747b-105">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6747b-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6747b-106">In This Section</span></span>  
 [<span data-ttu-id="6747b-107">Общие сведения о безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="6747b-107">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="6747b-108">Рассматриваются основные принципы безопасности транспорта в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6747b-108">Explains the basics of transport security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="6747b-109">Безопасность транспорта HTTP</span><span class="sxs-lookup"><span data-stu-id="6747b-109">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
 <span data-ttu-id="6747b-110">Рассматривается способ реализации протокола SSL (или HTTPS) в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6747b-110">Explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="6747b-111">Основные сведения о проверке подлинности HTTP</span><span class="sxs-lookup"><span data-stu-id="6747b-111">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)  
 <span data-ttu-id="6747b-112">Описываются схемы проверки подлинности HTTP, такие как обычная проверка подлинности, дайджест-проверка подлинности, NTLM и прочие.</span><span class="sxs-lookup"><span data-stu-id="6747b-112">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="6747b-113">Использование олицетворения при обеспечении безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="6747b-113">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 <span data-ttu-id="6747b-114">Рассматриваются пять уровней олицетворения, возможных благодаря режиму безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="6747b-114">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="6747b-115">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="6747b-115">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="6747b-116">Пошаговое руководство по основам настройки порта компьютера с помощью сертификата X.509 для безопасности транспорта SSL.</span><span class="sxs-lookup"><span data-stu-id="6747b-116">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6747b-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6747b-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="6747b-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6747b-118">Related Sections</span></span>  
 [<span data-ttu-id="6747b-119">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6747b-119">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="6747b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6747b-120">See Also</span></span>  
 [<span data-ttu-id="6747b-121">Программирование безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="6747b-121">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
