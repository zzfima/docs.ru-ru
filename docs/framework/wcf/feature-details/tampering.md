---
title: Подделка
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: 7a4265c30a6713f9557de2b3d1e99c87b7dd3e58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703391"
---
# <a name="tampering"></a>Подделка
*Незаконное изменение* — это процесс изменения сообщения или доставки сообщения и использования в целях, отличных от он был предназначен для измененного сообщения.  
  
## <a name="do-not-disable-ws-addressing"></a>Не отключайте WS-Addressing  
 Спецификация WS-Addressing расставляет заголовки адресов на каждом сообщении, по которым получатель сообщения проверяет отправителя сообщения. Чтобы отключить эту возможность, необходимо задать для свойства <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Если для режима безопасности задано значение Message и WS-Addressing отключена, злоумышленник сможет отправить запрос клиента другой службе, при этом вторая служба не сможет определить, что сообщение поступило от исходного клиента. Фактически, первая служба при взаимодействии со второй может выдавать себя за клиента.  
  
 Во избежание этого никогда не задавайте свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> и старайтесь не использовать <xref:System.ServiceModel.Channels.MessageVersion>, например статическое свойство <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>, задающее свойству <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> значение <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>См. также

- [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Раскрытие информации](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Повышение привилегий](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)
- [Отказ в обслуживании](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
- [Атаки с повторением](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
