---
title: "Практическое руководство. Выключение шифрования цифровых сигнатур | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd174313-ad81-4dca-898a-016ccaff8187
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Практическое руководство. Выключение шифрования цифровых сигнатур
По умолчанию сообщение подписывается и цифровая подпись шифруется.  Этим процессом можно управлять, создавая пользовательскую привязку с экземпляром элемента <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и присваивая свойству `MessageProtectionOrder` каждого класса значение перечисления <xref:System.ServiceModel.Security.MessageProtectionOrder>.  Значение по умолчанию — <xref:System.ServiceModel.Security.MessageProtectionOrder>.  Этот процесс занимает на 30 процентов больше времени, чем подпись и шифрование на основе полного размера сообщения \(чем меньше сообщение, тем больше влияние на производительность\).  Однако в случае отключения шифрования подписи злоумышленник может распознать содержимое сообщения.  Это обусловлено тем, что элемент подписи содержит хэш\-код обычного текста каждой подписанной части сообщения.  Например, хотя тело сообщения шифруется по умолчанию, нешифрованная подпись содержит хэш\-код тела сообщения до шифрования.  Если набор возможных значений для подписанной и зашифрованной части невелик, злоумышленник может понять содержимое, просмотрев хэш\-значение.  Шифрование подписи уменьшает вектор атак.  
  
 Таким образом, отключать шифрование подписи рекомендуется только тогда, когда содержимое имеет невысокую ценность или набор возможных значений содержимого велик и недетерминирован, и производительность имеет более высокое значение, чем снижение вероятности атаки, описанной выше.  
  
> [!NOTE]
>  Если никакая часть сообщения не шифруется, элемент подписи также не шифруется, даже если свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> присвоено значение <xref:System.ServiceModel.Security.MessageProtectionOrder>.  Это поведение возникает даже с привязками, предоставляемыми системой; у всех предоставляемых системой привязок порядку защиты сообщений задано значение `SignBeforeEncryptAndEncryptSignature`.  Однако в создаваемом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] языке описания служб \(WSDL\) все равно будет содержаться утверждение `<sp:EncryptSignature>`.  
  
### Отключение цифровой подписи  
  
1.  Создайте таблицу <xref:System.ServiceModel.Channels.CustomBinding>.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2.  Добавьте в коллекцию привязок элемент <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3.  Присвойте свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> значение <xref:System.ServiceModel.Security.MessageProtectionOrder> или присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> значение <xref:System.ServiceModel.Security.MessageProtectionOrder>.  
  
## См. также  
 [Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)