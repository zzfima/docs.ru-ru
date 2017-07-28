---
title: "Соображения о защите безопасных сеансов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Соображения о защите безопасных сеансов
Необходимо принять во внимание следующие элементы, влияющие на безопасность при реализации безопасных сеансов.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] вопросах безопасности см. в разделах [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) и [Рекомендации по безопасности](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## Безопасные сеансы и метаданные  
 Когда безопасный сеанс установлен и для свойства <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> задано значение `false`, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] передает проверочное утверждение `mssp:MustNotSendCancel` в качестве компонента метаданных в документе WSDL для конечной точки службы.Проверочное утверждение `mssp:MustNotSendCancel` информирует клиентов о том, что служба не отвечает на запросы, чтобы отменить безопасный сеанс.Если для свойства <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> задано значение `true`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не выдает проверочное утверждение `mssp:MustNotSendCancel` в документе WSDL.Предполагается, что если безопасный сеанс клиентам больше не требуется, они передают службе запрос отмены.Когда клиент создается с помощью программы [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), код клиента реагирует соответствующим образом на наличие или отсутствие проверочного утверждения `mssp:MustNotSendCancel`.  
  
## Безопасные диалоги и пользовательские маркеры  
 Из\-за определения, сделанного в спецификации WS\-SecureConversation, существует несколько проблем, связанных со смешиванием пользовательских маркеров и производных ключей.В этой спецификации говорится, что `wsse:SecurityTokenReference` — необязательный элемент, который ссылается на производный маркер «`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` Этот необязательный элемент используется для указания маркера контекста безопасности или общего ключа\/секрета, используемого для формирования ключа.Если указанные компоненты не заданы, предполагается, что получатель может определить общий ключ из контекста сообщения.Если контекст определить невозможно, должен произойти сбой `wsc:UnknownDerivationSource`”.  
  
 Это означает, что если требуется получить пользовательский маркер, необходимо зашифровать его тип предложения в элементе `SecurityTokenReference`.Формирование ключей можно отключить, но по умолчанию ключи формируются.Если ключ не шифруется, сериализация маркера производного ключа происходит успешно, но при попытке десериализовать его вызывается исключение.  
  
## См. также  
 [Как упорядочить отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)   
 [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Рекомендации по безопасности](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)