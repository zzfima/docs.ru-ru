---
title: "Возможности безопасности при использовании пользовательских привязок | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
caps.latest.revision: 11
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 11
---
# Возможности безопасности при использовании пользовательских привязок
Основные задачи обеспечения безопасности можно выполнить, используя одну из предоставляемых системой привязок.Однако при необходимости в дополнительных элементах управления вы можете создать пользовательскую привязку с помощью элемента<xref:System.ServiceModel.Channels.SecurityBindingElement>, следуя объяснениям в этом разделе.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о пользовательских привязках см. в разделе [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## В этом подразделе  
 [Режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 Содержит описание режимов проверки подлинности, которые возможны для пользовательской привязки.  
  
 [Как создавать пользовательскую привязку с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Содержит описание основных шагов, которые необходимо предпринять для создания пользовательской привязки к элементу безопасности.  
  
 [Как создать SecurityBindingElement для заданного режима проверки подлинности](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Описывается, как создать элемент безопасности для заданного режима проверки подлинности.  
  
 [Как упорядочить отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Описывается, как отключить безопасные сеансы при создании службы федерации.  
  
 [Как включить обнаружение повтора сообщений](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 Описывается, как определить, когда будет осуществлена атака воспроизведения.  
  
 [Практическое руководство. Создание подтверждающих учетных данных](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 Описывается, как предоставить службе подтверждающие учетные данные при необходимости.  
  
 [Как настраивать подтверждение сигнатуры](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 Содержит описание шагов, которые необходимо предпринять для подтверждения подписей при использовании цифровых подписей сообщений.  
  
 [Как установить максимальную разницу в показаниях часов](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 Описывается, как настроить максимально допустимую разницу во времени между службой и клиентом.  
  
 [Практическое руководство. Выключение шифрования цифровых сигнатур](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 Описывается, как отключение шифрования цифровых подписей может увеличить производительность.  
  
## Ссылка  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## Связанные подразделы  
 [Основные сведения об уровне защиты](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [Защита служб и клиентов](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## См. также  
 [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)   
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)