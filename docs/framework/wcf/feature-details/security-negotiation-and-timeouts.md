---
title: Согласование безопасности и тайм-ауты
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: dfabdb05c7658e3cf9eb5b325597360bbc0bb588
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153411"
---
# <a name="security-negotiation-and-timeouts"></a>Согласование безопасности и тайм-ауты
При проверки подлинности клиентов и служб Windows Communication Foundation (WCF) поддерживает режим, где учетные данные службы согласовываются в ходе проверки подлинности. В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту. Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>. Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ". Если согласование завершается за один цикл, время ожидания не используется.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [Инструкции: Установка разницы в показаниях часов Max](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
