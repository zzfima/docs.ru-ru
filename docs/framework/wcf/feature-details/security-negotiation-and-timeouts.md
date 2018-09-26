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
# <a name="security-negotiation-and-timeouts"></a>Согласование безопасности и тайм-ауты
При проверки подлинности клиентов и служб Windows Communication Foundation (WCF) поддерживает режим, где учетные данные службы согласовываются в ходе проверки подлинности. В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту. Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>. Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ". Если согласование завершается за один цикл, время ожидания не используется.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [Практическое руководство. Установка максимальной разницы в показаниях часов](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
