---
title: Практическое руководство. Выключение шифрования цифровых сигнатур
ms.date: 03/30/2017
ms.assetid: fd174313-ad81-4dca-898a-016ccaff8187
ms.openlocfilehash: 461c5af2c7fbb98486a8decbe4aa998d8d21070d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911175"
---
# <a name="how-to-disable-encryption-of-digital-signatures"></a>Практическое руководство. Выключение шифрования цифровых сигнатур
По умолчанию сообщение подписывается и цифровая подпись шифруется. Этим процессом можно управлять, создавая пользовательскую привязку с экземпляром элемента <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и присваивая свойству `MessageProtectionOrder` каждого класса значение перечисления <xref:System.ServiceModel.Security.MessageProtectionOrder>. Значение по умолчанию — <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Этот процесс занимает на 30 процентов больше времени, чем подпись и шифрование на основе полного размера сообщения (чем меньше сообщение, тем больше влияние на производительность). Однако в случае отключения шифрования подписи злоумышленник может распознать содержимое сообщения. Это обусловлено тем, что элемент подписи содержит хэш-код обычного текста каждой подписанной части сообщения. Например, хотя тело сообщения шифруется по умолчанию, нешифрованная подпись содержит хэш-код тела сообщения до шифрования. Если набор возможных значений для подписанной и зашифрованной части невелик, злоумышленник может понять содержимое, просмотрев хэш-значение. Шифрование подписи уменьшает вектор атак.  
  
 Таким образом, отключать шифрование подписи рекомендуется только тогда, когда содержимое имеет невысокую ценность или набор возможных значений содержимого велик и недетерминирован, и производительность имеет более высокое значение, чем снижение вероятности атаки, описанной выше.  
  
> [!NOTE]
> Если никакая часть сообщения не шифруется, элемент подписи также не шифруется, даже если свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> присвоено значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Это поведение возникает даже с привязками, предоставляемыми системой; у всех предоставляемых системой привязок порядку защиты сообщений задано значение `SignBeforeEncryptAndEncryptSignature`. Тем не менее, созданное на языке WSDL значение WCF по-прежнему будет содержать `<sp:EncryptSignature>` утверждение.  
  
### <a name="to-disable-digital-signing"></a>Отключение цифровой подписи  
  
1. Создайте таблицу <xref:System.ServiceModel.Channels.CustomBinding>. Дополнительные сведения см. в разделе [Практическое руководство. Создайте пользовательскую привязку с помощью](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)SecurityBindingElement.  
  
2. Добавьте в коллекцию привязок элемент <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3. Присвойте свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> или присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.  
  
## <a name="see-also"></a>См. также

- [Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
