---
title: Согласование безопасности и тайм-ауты
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: a02c9d7b42eadf9a5ce9af8022fe292d6c23249c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748295"
---
# <a name="security-negotiation-and-timeouts"></a>Согласование безопасности и тайм-ауты
При проверки подлинности клиентов и служб Windows Communication Foundation (WCF) поддерживает режим, где учетные данные службы согласовываются в ходе проверки подлинности. В таких случаях между клиентом и службой может происходить взаимный обмен информацией для распространения учетных данных службы клиенту. Продолжительность этого взаимного обмена определяется свойством <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>. Однако это время ожидания применяется, только если обмен информацией фактически продолжается дольше одного цикла "запрос-ответ". Если согласование завершается за один цикл, время ожидания не используется.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Практическое руководство. Установка разницы в показаниях часов Max](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
