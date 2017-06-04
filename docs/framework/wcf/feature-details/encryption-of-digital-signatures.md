---
title: "Шифрование цифровых сигнатур | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "цифровые сигнатуры [WCF]"
  - "цифровые сигнатуры [WCF], шифрование"
  - "шифрование цифровых сигнатур [WCF]"
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Шифрование цифровых сигнатур
По умолчанию сообщение подписывается и шифруется, и цифровая подпись шифруется.Этим процессом можно управлять, создавая пользовательскую привязку с экземпляром элемента <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и затем присваивая свойству `MessageProtectionOrder` каждого класса значение перечисления <xref:System.ServiceModel.Security.MessageProtectionOrder>.Значение по умолчанию — <xref:System.ServiceModel.Security.MessageProtectionOrder>.Этот процесс занимает на 10 — 40 процентов больше времени, чем просто подписывание и шифрование.Однако в случае отключения шифрования подписи злоумышленник может распознать содержимое сообщения.Это обусловлено тем, что элемент подписи содержит хэш\-код обычного текста каждой подписанной части сообщения.Например, хотя тело сообщения шифруется по умолчанию, нешифрованная подпись содержит хэш\-код тела сообщения.Если сообщение короткое, злоумышленник может определить содержимое.Шифрование подписи уменьшает или исключает эту возможность.  
  
 Поэтому отключайте шифрование подписи только при малой важности содержимого и существенном повышении производительности в результате такого отключения, например при передаче больших двоичных файлов, не критичных к нарушениям безопасности.  
  
### Отключение цифровой подписи  
  
1.  Создайте привязку <xref:System.ServiceModel.Channels.CustomBinding>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2.  Добавьте в коллекцию привязок элемент <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3.  Присвойте свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> значение <xref:System.ServiceModel.Security.MessageProtectionOrder> или присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=fullName> значение <xref:System.ServiceModel.Security.MessageProtectionOrder>.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] о создании пользовательских привязок см. в разделе [Создание пользовательских привязок](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о создании пользовательской привязки для конкретного режима аутентификации см. в разделе [Как создать SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## См. также  
 <xref:System.ServiceModel.Security.MessageProtectionOrder>   
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Создание пользовательских привязок](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)   
 [Как создать SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)