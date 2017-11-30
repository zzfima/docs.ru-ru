---
title: "Подделка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d8852c4d19c48af2beee598f4ddfae7b775a025f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
 [Повышение прав доступа](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Отказ в обслуживании](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 [Атаки с повторением пакетов](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
