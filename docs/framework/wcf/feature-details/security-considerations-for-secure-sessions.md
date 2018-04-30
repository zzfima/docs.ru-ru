---
title: Соображения о защите безопасных сеансов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 4d1e5082ace452eabddd91a45a20c6d6363e118b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="security-considerations-for-secure-sessions"></a>Соображения о защите безопасных сеансов
Необходимо принять во внимание следующие элементы, влияющие на безопасность при реализации безопасных сеансов. Дополнительные сведения о вопросах безопасности см. в разделе [вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) и [рекомендации по безопасности](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Безопасные сеансы и метаданные  
 Когда безопасный сеанс установлен и для свойства <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> задано значение `false`, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] передает проверочное утверждение `mssp:MustNotSendCancel` в качестве компонента метаданных в документе WSDL для конечной точки службы. Проверочное утверждение `mssp:MustNotSendCancel` информирует клиентов о том, что служба не отвечает на запросы, чтобы отменить безопасный сеанс. Если для свойства <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> задано значение `true`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не выдает проверочное утверждение `mssp:MustNotSendCancel` в документе WSDL. Предполагается, что если безопасный сеанс клиентам больше не требуется, они передают службе запрос отмены. Когда клиент создается с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), клиентский код соответствующим образом реагирует на наличие или отсутствие `mssp:MustNotSendCancel` утверждения.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Безопасные диалоги и пользовательские маркеры  
 Из-за определения, сделанного в спецификации WS-SecureConversation, существует несколько проблем, связанных со смешиванием пользовательских маркеров и производных ключей. Спецификации говорится, что `wsse:SecurityTokenReference` — это необязательный элемент, который ссылается на производный маркер: «`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` Этот необязательный элемент используется для указания маркера контекста безопасности, маркер безопасности или общий ключ/секрет, используемый для формирования ключа. Если указанные компоненты не заданы, предполагается, что получатель может определить общий ключ из контекста сообщения. Если не удалось определить контекст, затем сбой `wsc:UnknownDerivationSource` должно вызываться.»  
  
 Это означает, что если требуется получить пользовательский маркер, необходимо зашифровать его тип предложения в элементе `SecurityTokenReference`. Формирование ключей можно отключить, но по умолчанию ключи формируются. Если ключ не шифруется, сериализация маркера производного ключа происходит успешно, но при попытке десериализовать его вызывается исключение.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Рекомендации по безопасности](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
