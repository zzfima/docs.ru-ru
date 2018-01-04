---
title: "Согласование безопасности и тайм-ауты"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 6fbee18d31cb1774300c14587b0f7d973a4996ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="security-negotiation-and-timeouts"></a>Согласование безопасности и тайм-ауты
Когда клиенты и службы проходят проверку подлинности, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поддерживает режим, в котором в ходе проверки подлинности осуществляется согласование учетных данных. В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту. Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>. Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ". Если согласование завершается за один цикл, время ожидания не используется.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [Практическое руководство. Установка максимальной разницы в показаниях часов](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
