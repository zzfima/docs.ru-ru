---
title: Подделка
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: 519881a0813ac0b9f9218db42a42723a19a3089c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tampering"></a>Подделка
*Подмены* — это процесс изменения сообщения или доставки сообщения и использования измененного сообщения в целях, отличных от он был предназначен для.  
  
## <a name="do-not-disable-ws-addressing"></a>Не отключайте WS-Addressing  
 Спецификация WS-Addressing расставляет заголовки адресов на каждом сообщении, по которым получатель сообщения проверяет отправителя сообщения. Чтобы отключить эту функцию, необходимо задать для свойства <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Если для режима безопасности задано значение Message и WS-Addressing отключена, злоумышленник сможет отправить запрос клиента другой службе, при этом вторая служба не сможет определить, что сообщение поступило от исходного клиента. Фактически, первая служба при взаимодействии со второй может выдавать себя за клиента.  
  
 Во избежание этого никогда не задавайте свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> и старайтесь не использовать <xref:System.ServiceModel.Channels.MessageVersion>, например статическое свойство <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>, задающее свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>См. также  
 [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Раскрытие информации](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [Повышение привилегий](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Отказ в обслуживании](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 [Атаки с повторением](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
