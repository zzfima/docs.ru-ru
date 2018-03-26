---
title: WSDL и политика
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd52e36199fc2412abb003d530dd5614cda8049b
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="wsdl-and-policy"></a>WSDL и политика
В данном разделе приводятся сведения о реализации WSDL 1.1, WS-Policy и WS-PolicyAttachment [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], а также описываются дополнительные утверждения WS-Policy и расширения WSDL 1.1, впервые представленные в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификации WS-Policy и WS-PolicyAttachment, переданные W3C с ограничениями и пояснениями, представленными в этом документе.  
  
 В этом документе используются префиксы и пространства имен, приведенные в следующей таблице.  
  
|Префикс|Пространство имен|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|http://schemas.xmlsoap.org/ws/2004/09/policy|  
|wsp (WS-Policy 1.5)|http://www.w3.org/ns/ws-policy|  
|http|http://schemas.microsoft.com/ws/06/2004/policy/http|  
|msmq|http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq|  
|msf|http://schemas.microsoft.com/ws/2006/05/framing/policy|  
|mssp|http://schemas.microsoft.com/ws/2005/07/securitypolicy|  
|msc|http://schemas.microsoft.com/ws/2005/12/wsdl/contract|  
|cdp|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="wcf-wsdl11-extensions"></a>Расширения WCF WSDL1.1  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует следующие расширения WSDL1.1 для описания требований сеанса контракта.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 xs:boolean, показывает, что эта операция инициирует сеанс [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]; значение по умолчанию - `false`.  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 xs:boolean, показывает, что эта операция завершает сеанс [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]; значение по умолчанию - `false`.  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 xs:boolean, показывает, что этот контракт требует установления сеанса.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>Универсальные коды ресурса (URI) транспорта привязки SOAP 1.x HTTP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует следующие URI для указания транспортов, которые следует использовать с элементами расширения привязок WSDL 1.1, SOAP 1.1 и SOAP 1.2.  
  
|Transport|URI|  
|---------------|---------|  
|HTTP|http://schemas.xmlsoap.org/soap/http|  
|TCP|http://schemas.microsoft.com/soap/tcp|  
|MSMQ|http://schemas.microsoft.com/soap/msmq|  
|Именованные каналы|http://schemas.microsoft.com/soap/named-pipe|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Утверждения политики, реализуемые WCF  
 Помимо утверждений политики, представленных в спецификациях веб-служб (WS-*) и описываемых в других разделах этого документа, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует следующие утверждения политики.  
  
|Утверждение политики|Субъект политики|Описание|  
|----------------------|--------------------|-----------------|  
|http:HttpBasicAuthentication|Конечная точка|Конечная точка использует обычную проверку подлинности HTTP.|  
|http:HttpDigestAuthentication|Конечная точка|Конечная точка использует дайджест-проверку подлинности HTTP.|  
|http:HttpNegotiateAuthentication|Конечная точка|Конечная точка использует согласованную проверку подлинности HTTP.|  
|http:HttpNtlmAuthentication|Конечная точка|Конечная точка использует проверку подлинности HTTP NTLM.|  
|msf:Streamed|Конечная точка|Конечная точка использует кадрирование потокового сообщения. Это утверждение используется с протоколом кадрирования сообщения, предоставляемого для таких транспортов как TCP и именованные каналы.|  
|msf:SslTransportSecurity|Конечная точка|Конечная точка использует с кадрированием сообщения безопасность на уровне транспорта (TLS).|  
|msf:WindowsTransportSecurity|Конечная точка|Конечная точка использует с кадрированием сообщения согласование с поставщиком безопасности (SPNEGO).|  
|msmq:MsmqBestEffort|Конечная точка|MSMQ с гарантиями наилучшего из возможного.|  
|msmq:MsmqSession|Конечная точка|MSMQ с гарантиями сеансов.|  
|msmq:MsmqVolatile|Конечная точка|Неустойчивый MSMQ.|  
|msmq:Authenticated|Конечная точка|Используется проверка подлинности с транспортом MSMQ.|  
|msmq:WindowsDomain|Конечная точка|MSMQ использует проверку подлинности домена Windows.|  
|cdp:CompositeDuplex|Конечная точка|Конечная точка использует два отдельных подключения встречных транспортов для входящих и исходящих сообщений.|  
|mssp:RsaToken|Вложенный|Утверждение маркера ключа RSA. Это требование, как правило, удовлетворяется ключом RSA, сериализуемым непосредственно как часть информации о ключе в разрешающей подписи.|  
|mssp:SslContextToken|Вложенный|Требует использования SecurityContextToken, полученного при подтверждении двоичного протокола TLS с помощью WS-Trust. Вложенные утверждения включают sp:RequireDerivedKeys, mssp:MustNotSendCancel и mssp:RequireClientCertificate.|  
|mssp:MustNotSendCancel|Вложенный|Задает требование о том, что сообщения запроса маркера безопасности (RST) [WS-Trust] с использованием привязки Cancel [WS-Trust, WS-SC] не должны отправляться издателю заданного SecurityContextToken. Если присутствует это утверждение, такие сообщения запроса не должны отправляться издателю. Если это утверждение отсутствует, такие сообщения запроса могут отправляться издателю.|  
|mssp:RequireClientCertificate|Вложенный|Этот необязательный элемент задает требование о том, что сертификат клиента должен предоставляться как часть протокола TLSNEGO. Если это утверждение присутствует, сертификат клиента должен быть предоставлен. Если это утверждение отсутствует, сертификат клиента предоставляться не должен. Это утверждение не должно использоваться за пределами mssp:SslContextToken.|  
  
## <a name="see-also"></a>См. также  
 [Пользовательская публикация WSDL](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)  
 [Практическое руководство. Экспорт пользовательской информации WSDL](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)  
 [Практическое руководство. Импорт пользовательской информации WSDL](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
