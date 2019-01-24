---
title: Согласование безопасности и тайм-ауты
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 38dce9bd6587850a5e3327600bb8bc13c48b93e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592618"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="e3a81-102">Согласование безопасности и тайм-ауты</span><span class="sxs-lookup"><span data-stu-id="e3a81-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="e3a81-103">При проверки подлинности клиентов и служб Windows Communication Foundation (WCF) поддерживает режим, где учетные данные службы согласовываются в ходе проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e3a81-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="e3a81-104">В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту.</span><span class="sxs-lookup"><span data-stu-id="e3a81-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="e3a81-105">Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3a81-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="e3a81-106">Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="e3a81-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="e3a81-107">Если согласование завершается за один цикл, время ожидания не используется.</span><span class="sxs-lookup"><span data-stu-id="e3a81-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a81-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e3a81-108">See also</span></span>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="e3a81-109">Практическое руководство. Установка разницы в показаниях часов Max</span><span class="sxs-lookup"><span data-stu-id="e3a81-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
