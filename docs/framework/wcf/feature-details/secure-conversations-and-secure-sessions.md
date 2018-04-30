---
title: Безопасные диалоги и безопасные сеансы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 502064ce30f6e117168834643a116d3983811fb8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="secure-conversations-and-secure-sessions"></a><span data-ttu-id="a55f7-102">Безопасные диалоги и безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="a55f7-102">Secure Conversations and Secure Sessions</span></span>
<span data-ttu-id="a55f7-103">Функцией [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является возможность установления безопасных сеансов между двумя конечными точками, проверяющими подлинность друг друга и согласующими процесс шифрования и цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="a55f7-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to establish secure sessions between two endpoints that authenticate each other and agree upon an encryption and digital signature process.</span></span> <span data-ttu-id="a55f7-104">Например, конечная точка службы может требовать, чтобы клиентская конечная точка передавала для проверки подлинности маркер безопасности, основанный на сертификате X.509.</span><span class="sxs-lookup"><span data-stu-id="a55f7-104">For example, the service endpoint might require a client endpoint to send a security token based upon an X.509 certificate for authentication.</span></span> <span data-ttu-id="a55f7-105">После завершения проверки подлинности клиента конечная точка службы возвращает клиенту маркер контекста безопасности (SCT), который затем используется для обеспечения безопасности всех последующих сообщений в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a55f7-105">Once the client is authenticated, the service endpoint returns a security context token (SCT) back to the client that is then used to secure all subsequent messages within the session.</span></span> <span data-ttu-id="a55f7-106">Установление такого безопасного сеанса повышает эффективность набора сообщений, которыми обмениваются эти две конечные точки, так как маркер SCT имеет симметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="a55f7-106">Establishing this secure session enables the set of messages that are exchanged between the two endpoints to be more efficient, because the SCT has a symmetric key.</span></span> <span data-ttu-id="a55f7-107">При создании цифровой подписи или шифровании набора данных асимметричные ключи, на которых основаны сертификаты X.509, требуют значительно большей вычислительной мощности, чем симметричные ключи.</span><span class="sxs-lookup"><span data-stu-id="a55f7-107">Asymmetric keys, which X.509 certificates are based upon, require significantly more computational power than symmetric keys when generating a digital signature or encrypting a set of data.</span></span>  
  
 <span data-ttu-id="a55f7-108">Политика начальной загрузки (заданные в разделе 6.2.7 [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) стандартные) содержит утверждения безопасности сообщений, используемый для защиты канала и проверки подлинности клиента до обмена RST/SCT и RSTR/SCT.</span><span class="sxs-lookup"><span data-stu-id="a55f7-108">The bootstrap policy (defined in section 6.2.7 of the [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) contains the message security assertions used to secure the channel and authenticate the client prior to the RST/SCT and RSTR/SCT exchange.</span></span> <span data-ttu-id="a55f7-109">Определенные стандартные привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обладают свойством `Security.Message.EstablishSecurityContext`, управляющим использованием безопасного диалога.</span><span class="sxs-lookup"><span data-stu-id="a55f7-109">Certain [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standard bindings have a `Security.Message.EstablishSecurityContext` property which controls whether secure conversation is used.</span></span> <span data-ttu-id="a55f7-110">При использовании пользовательских привязок программу начальной загрузки обозначается вложенности элементов привязки безопасности, либо с помощью [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) в файле конфигурации или вызвав <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> в коде.</span><span class="sxs-lookup"><span data-stu-id="a55f7-110">When using custom bindings the bootstrap is indicated by nesting security binding elements, either through [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in the configuration file, or by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> in code.</span></span>  
  
 <span data-ttu-id="a55f7-111">Дополнительные сведения о сеансах см. в разделе [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="a55f7-111">For more information about sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55f7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a55f7-112">See Also</span></span>  
 [<span data-ttu-id="a55f7-113">Сеансы, экземпляры и параллелизм</span><span class="sxs-lookup"><span data-stu-id="a55f7-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="a55f7-114">Практическое руководство. Создание службы, для которой требуются сеансы</span><span class="sxs-lookup"><span data-stu-id="a55f7-114">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
