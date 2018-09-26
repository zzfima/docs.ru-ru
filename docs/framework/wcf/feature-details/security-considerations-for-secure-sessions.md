---
title: Соображения о защите безопасных сеансов
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
author: BrucePerlerMS
ms.openlocfilehash: 470ffc007ed73b28beba24bd0eb9c670dea9337d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199974"
---
# <a name="security-considerations-for-secure-sessions"></a>Соображения о защите безопасных сеансов
Необходимо принять во внимание следующие элементы, влияющие на безопасность при реализации безопасных сеансов. Дополнительные сведения о вопросах безопасности см. в разделе [вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) и [рекомендации по обеспечению безопасности](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Безопасные сеансы и метаданные  
 Если установлен безопасный сеанс и <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> свойству `false`, Windows Communication Foundation (WCF) отправляет `mssp:MustNotSendCancel` утверждения как часть метаданных в документе языка описания служб (WSDL) для Конечная точка службы. Проверочное утверждение `mssp:MustNotSendCancel` информирует клиентов о том, что служба не отвечает на запросы, чтобы отменить безопасный сеанс. Когда <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> свойству `true`, то WCF не выдает `mssp:MustNotSendCancel` утверждение в документе WSDL. Предполагается, что если безопасный сеанс клиентам больше не требуется, они передают службе запрос отмены. Когда клиент создается с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), код клиента реагирует соответствующим образом на наличие или отсутствие `mssp:MustNotSendCancel` утверждения.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Безопасные диалоги и пользовательские маркеры  
 Из-за определения, сделанного в спецификации WS-SecureConversation, существует несколько проблем, связанных со смешиванием пользовательских маркеров и производных ключей. Спецификации говорится, что `wsse:SecurityTokenReference` является необязательным элементом, который ссылается на производный маркер: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` Этот необязательный элемент используется для указания маркера контекста безопасности, маркера безопасности или общего ключа/секрета, используемого для формирования ключа. Если указанные компоненты не заданы, предполагается, что получатель может определить общий ключ из контекста сообщения. Если контекст не может быть определен, то сбой `wsc:UnknownDerivationSource` должно вызываться.»  
  
 Это означает, что если требуется получить пользовательский маркер, необходимо зашифровать его тип предложения в элементе `SecurityTokenReference`. Формирование ключей можно отключить, но по умолчанию ключи формируются. Если ключ не шифруется, сериализация маркера производного ключа происходит успешно, но при попытке десериализовать его вызывается исключение.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [Вопросы безопасности](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Рекомендации по безопасности](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
