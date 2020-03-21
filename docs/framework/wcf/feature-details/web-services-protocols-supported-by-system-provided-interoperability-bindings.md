---
title: Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: a1e67401a09370a46bc7a3e8546c95467bc18b67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184144"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками
Фонд связи Windows (WCF) создан для взаимодействия с web-сервисами, поддерживающими набор спецификаций, известных как спецификации Web-сервисов. Для упрощения конфигурации сервиса для наилучшей совместимости, WCF вводит три <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>совместимых системных привязки: <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>, и <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Для совместимости с Организацией по улучшению стандартов структурированной информации (OASIS) WCF включает в <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>себя одну совместимую систему, предоставленную привязкой: . Для публикации метаданных WCF включает в себя две совместимые системы, предоставленные привязки: [ \<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) и [ \<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). В этом разделе перечислены спецификации, поддерживаемые предоставляемыми системой привязками с возможностью взаимодействия.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Протоколы веб-служб, поддерживаемые привязками basicHttpBinding, wsHttpBinding, ws2007HttpBinding и wsDualHttpBinding  
  
### <a name="all-bindings"></a>Все привязки  
 [ \<BasicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), и [ \<ws2007HttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) привязки поддерживают следующие протоколы.  
  
> [!NOTE]
> Сведения о привязках, используемых для публикации метаданных, см. в разделе "Предоставляемые системой привязки метаданных" ниже.  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Транспортировка|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> `BasicHttpBinding`, `WSHttpBinding`, и `WS2007HttpBinding` используют протоколы HTTP и HTTPS.|  
|Обмен сообщениями|MTOM|[MTOM](https://www.w3.org/TR/soap12-mtom/)<br /><br /> `basicHttpBinding`, `wsHttpBinding` и `ws2007HttpBinding` поддерживают механизм оптимизации передачи сообщений (MTOM). По умолчанию не используется. Чтобы использовать MTOM, присвойте атрибуту `messageEncoding` значение `"Mtom"`.<br /><br /> Пример<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Метаданные|WSDL 1.1|[WSDL 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF использует язык описания веб-служб (WSDL) для описания служб.|  
|Метаданные|WS-Policy|[WS-Policy](https://www.w3.org/Submission/WS-Policy/)<br /><br /> WCF использует спецификацию WS-Policy вместе с утверждениями, кончаемыми для домена, для описания требований и возможностей службы.|  
|Метаданные|WS-Policy 1.5|[WS-Policy 1.5](https://www.w3.org/TR/2007/CR-ws-policy-20070605/)<br /><br /> WCF использует спецификацию WS-Policy вместе с утверждениями, кончаемыми для домена, для описания требований и возможностей службы.|  
|Метаданные|WS-PolicyAttachment|[WS-PolicyAttachment](http://specs.xmlsoap.org/ws/2004/09/policy/ws-policyattachment.pdf)<br /><br /> WCF реализует WS-PolicyAttachment для прикрепления выражений политики в различных областях на языке описания веб-служб (WSDL).|  
|Метаданные|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF реализует WS-MetadataExchange для получения XML Schema, WSDL и WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Обмен сообщениями|SOAP 1,1|[SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)<br /><br /> В соответствии со спецификацией Basic Profile 1.1 элемент `basicHttpBinding` реализует протокол обмена сообщениями SOAP 1.1.|  
|Безопасность|WSS SOAP Message Security 1.0|[WSS SOAP Безопасности сообщений 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> В соответствии со спецификацией Basic Security Profile элемент `basicHttpBinding` реализует спецификацию Web Services Security (WSS) SOAP Message Security 1.0 для имени пользователя/пароля и безопасности на основе сертификатов X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Безопасность|WSS SOAP Message Security UsernameToken Profile 1.0|[WSS SOAP Message Security UsernameToken Profile 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Безопасность|WSS SOAP Сообщение безопасности X.509 Профиль маркера сертификата 1.0|[WSS SOAP Сообщение безопасности X.509 Профиль маркера сертификата 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding и wsDualHttpBinding  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Обмен сообщениями|SOAP 1.2|[Руководство](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Платформа обмена сообщениями (на английском языке)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Дополнения (включая привязку HTTP) (на английском языке)](https://www.w3.org/TR/soap12-part2/)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)<br /><br /> Привязки `wsHttpBinding`, `ws2007HttpBinding` и `wsDualHttpBinding` реализуют рекомендацию спецификации WS-Addressing консорциума W3C (включение асинхронного обмена сообщениями, корреляции сообщений и механизмов адресации без привязки к конкретному транспортному протоколу).<br /><br /> WCF не поддерживает шифрование заголовков WS-Addressing, хотя это допускается спецификациями WS-*.|  
|Обмен сообщениями|WS-Addressing 1.0 ― метаданные|[WS-Адрес1 1.0 Метаданные](https://www.w3.org/2007/05/addressing/metadata/) Поддержка этого протокола включена путем установки версии политики в поведении ServiceMetadata - с набором политики 1.2 (по умолчанию), описание wsdl совместимо с WS-Addressing wsdl, с набором политики до 1.5, описание wsdl совместимо с метаданными ws-addressing.<br /><br /> WCF не поддерживает шифрование заголовков WS-Addressing, хотя это допускается спецификациями WS-*.|  
|Безопасность|WSS SOAP Message Security 1.0|[WSS SOAP Безопасности сообщений 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> Используется, когда атрибуту `securityMode` присвоено значение "wsSecurityOverHttp" (по умолчанию) и параметры настроены с использованием дочернего элемента `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Сообщение безопасности UsernameToken Профиль 1.1|[WSS SOAP Message Security UsernameToken Profile 1.0](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> Используется, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Username".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP Message Security X.509 Certificate Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)<br /><br /> Используется для защиты сообщений, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Username", "Certificate" или "None". Кроме того, используется для проверки подлинности клиентов, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Certificate".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Message Security Kerberos Token Profile 1.1|[WSS SOAP Сообщение безопасности Kerberos Токен Профиль 1.1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)<br /><br /> Используется для проверки подлинности и защиты сообщений, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Безопасность|WS-SecureConversation|[WS-SecureConversation](http://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> Используется для обеспечения безопасного сеанса, когда атрибуту `security/@mode` присвоено значение "Message", а атрибуту `message/@establishSecurityContext` присвоено значение "true" (по умолчанию).|  
|Безопасность|WS-Trust|[WS-Траст](http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf)<br /><br /> Используется в спецификации WS-SecureConversation (см. выше).|  
|Надежный обмен сообщениями|WS-ReliableMessaging|[WS-ReliableMessaging](http://specs.xmlsoap.org/ws/2005/02/rm/ws-reliablemessaging.pdf)<br /><br /> Используется, когда привязка настроена на использование свойства `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transactions|WS-AtomicTransaction|[WS-AtomicTransaction](http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)<br /><br /> Используется для обмена данными между диспетчерами транзакций. Клиенты и службы WCF всегда используют местных менеджеров транзакций.|  
|Transactions|WS-Coordination|[WS-Coordination](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))<br /><br /> Используется для передачи контекста транзакций, когда атрибуту `flowTransactions` присвоено значение Allowed или Required.<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding и ws2007FederationHttpBinding  
 wsFederationHttpBinding>и [ \<ws2007FederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) элементы введены для обеспечения поддержки федеративных сценариев, где третья сторона выдает маркер, используемый для проверки подлинности клиента. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) В дополнение к протоколам, используемым привязкой `wsHttpBinding`, привязка `wsFederationHttpBinding` позволяет использовать следующие спецификации:  
  
- `WS-Trust` для выдачи маркеров.  
  
- WSS Security Assertions Markup Language (SAML) Token Profile 1.0 и 1.1 для наиболее часто выдаваемого формата маркеров.  
  
 Пример  
  
```xml  
<wsFederationHttpBinding>  
  <binding name="myBinding">  
     <security mode="Message">  
       <message issuedKeyType="Symmetric"
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
         <issuerMetadata address =
         'http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex'>  
       </message>  
     </security>  
  </binding>  
</wsFederationHttpBinding>  
```  
  
 Для получения дополнительной информации [см.](../../../../docs/framework/wcf/feature-details/federation.md)  
  
## <a name="system-provided-metadata-bindings"></a>Предоставляемые системой привязки метаданных  
 В следующих таблицах приведены протоколы, поддерживаемые предоставляемыми системой привязками метаданных, которые предоставляются классом <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 [ \<Связывание mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) поддерживает следующие протоколы. Для получения дополнительной информации об использовании этой привязки [см. Издательский Метаданные](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Транспортировка|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)|  
|Обмен сообщениями|SOAP 1.2|[Руководство](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Платформа обмена сообщениями (на английском языке)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Дополнения (включая привязку HTTP) (на английском языке)](https://www.w3.org/TR/soap12-part2/)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Метаданные|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF реализует WS-MetadataExchange для получения XML Schema, WSDL и WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 mexHttpsBinding>поддерживает следующие протоколы. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) Для получения дополнительной информации об использовании этой привязки [см. Издательский Метаданные](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Транспортировка|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> Безопасность транспорта включена.|  
|Обмен сообщениями|SOAP 1.2|[Руководство](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Платформа обмена сообщениями (на английском языке)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Дополнения (включая привязку HTTP) (на английском языке)](https://www.w3.org/TR/soap12-part2/)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Метаданные|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF реализует WS-MetadataExchange для получения XML Schema, WSDL и WS-Policy.|  
  
## <a name="see-also"></a>См. также раздел

- [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<mexHttpsОбязательные>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
