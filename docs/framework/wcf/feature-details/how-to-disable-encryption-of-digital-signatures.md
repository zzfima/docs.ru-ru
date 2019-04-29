---
title: Практическое руководство. Выключение шифрования цифровых сигнатур
ms.date: 03/30/2017
ms.assetid: fd174313-ad81-4dca-898a-016ccaff8187
ms.openlocfilehash: e2fd2a058e636ebf398f9d0c71a93788ccd7dfa0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773195"
---
# <a name="how-to-disable-encryption-of-digital-signatures"></a>Практическое руководство. Выключение шифрования цифровых сигнатур
По умолчанию сообщение подписывается и цифровая подпись шифруется. Этим процессом можно управлять, создавая пользовательскую привязку с экземпляром элемента <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и присваивая свойству `MessageProtectionOrder` каждого класса значение перечисления <xref:System.ServiceModel.Security.MessageProtectionOrder>. Значение по умолчанию — <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Этот процесс занимает на 30 процентов больше времени, чем подпись и шифрование на основе полного размера сообщения (чем меньше сообщение, тем больше влияние на производительность). Однако в случае отключения шифрования подписи злоумышленник может распознать содержимое сообщения. Это обусловлено тем, что элемент подписи содержит хэш-код обычного текста каждой подписанной части сообщения. Например, хотя тело сообщения шифруется по умолчанию, нешифрованная подпись содержит хэш-код тела сообщения до шифрования. Если набор возможных значений для подписанной и зашифрованной части невелик, злоумышленник может понять содержимое, просмотрев хэш-значение. Шифрование подписи уменьшает вектор атак.  
  
 Таким образом, отключать шифрование подписи рекомендуется только тогда, когда содержимое имеет невысокую ценность или набор возможных значений содержимого велик и недетерминирован, и производительность имеет более высокое значение, чем снижение вероятности атаки, описанной выше.  
  
> [!NOTE]
>  Если никакая часть сообщения не шифруется, элемент подписи также не шифруется, даже если свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> присвоено значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Это поведение возникает даже с привязками, предоставляемыми системой; у всех предоставляемых системой привязок порядку защиты сообщений задано значение `SignBeforeEncryptAndEncryptSignature`. Однако описания служб Language (WSDL) WCF создает будет по-прежнему содержать `<sp:EncryptSignature>` утверждения.  
  
### <a name="to-disable-digital-signing"></a>Отключение цифровой подписи  
  
1. Создайте таблицу <xref:System.ServiceModel.Channels.CustomBinding>. Дополнительные сведения см. в разделе [Как Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2. Добавьте в коллекцию привязок элемент <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3. Присвойте свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> или присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.  
  
## <a name="see-also"></a>См. также

- [Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
