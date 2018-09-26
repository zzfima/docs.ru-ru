---
title: Согласование безопасности и тайм-ауты
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
author: BrucePerlerMS
ms.openlocfilehash: 6b6c9c6ed44eb3ebefb21f2fbff1e73171262ed7
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088312"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="ef30a-102">Согласование безопасности и тайм-ауты</span><span class="sxs-lookup"><span data-stu-id="ef30a-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="ef30a-103">При проверки подлинности клиентов и служб Windows Communication Foundation (WCF) поддерживает режим, где учетные данные службы согласовываются в ходе проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ef30a-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="ef30a-104">В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту.</span><span class="sxs-lookup"><span data-stu-id="ef30a-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="ef30a-105">Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="ef30a-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="ef30a-106">Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="ef30a-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="ef30a-107">Если согласование завершается за один цикл, время ожидания не используется.</span><span class="sxs-lookup"><span data-stu-id="ef30a-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef30a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ef30a-108">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [<span data-ttu-id="ef30a-109">Практическое руководство. Установка максимальной разницы в показаниях часов</span><span class="sxs-lookup"><span data-stu-id="ef30a-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
