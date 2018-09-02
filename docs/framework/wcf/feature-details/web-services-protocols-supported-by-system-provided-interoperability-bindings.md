---
title: Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: f4967a29b28f1862f5799f6935083ed12cb81ead
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399054"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками
Windows Communication Foundation (WCF) предназначено для взаимодействия с веб-службами, поддерживающими набор спецификаций, называемых спецификациями веб-служб. Чтобы упростить конфигурацию службы для рекомендации по взаимодействию, WCF представляет три с возможностью взаимодействия предоставляемых системой привязок: <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>, <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>, и <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Для обеспечения взаимодействия с организация для продвижения из структурированных сведения стандартов OASIS-стандартов, WCF включает в себя одну привязку с возможностью системных: <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>. Для публикации метаданных WCF включает в себя два с возможностью взаимодействия предоставляемых системой привязок: [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) и [ \<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). В этом разделе перечислены спецификации, поддерживаемые предоставляемыми системой привязками с возможностью взаимодействия.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Протоколы веб-служб, поддерживаемые привязками basicHttpBinding, wsHttpBinding, ws2007HttpBinding и wsDualHttpBinding  
  
### <a name="all-bindings"></a>Все привязки  
 [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), и [ \<ws2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) поддержка привязки следующие протоколы.  
  
> [!NOTE]
>  Сведения о привязках, используемых для публикации метаданных, см. в разделе "Предоставляемые системой привязки метаданных" ниже.  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`, `WSHttpBinding`, и `WS2007HttpBinding` используют протоколы HTTP и HTTPS.|  
|Обмен сообщениями|MTOM|[MTOM](https://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`, `wsHttpBinding` и `ws2007HttpBinding` поддерживают механизм оптимизации передачи сообщений (MTOM). По умолчанию не используется. Чтобы использовать MTOM, присвойте атрибуту `messageEncoding` значение `"Mtom"`.<br /><br /> Пример<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Метаданные|WSDL 1.1|[WSDL 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF использует язык описания веб-служб (WSDL) для описания служб.|  
|Метаданные|WS-Policy|[WS-Policy](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> WCF используется спецификация WS-Policy вместе с доменными утверждениями для описания требований и возможностей служб.|  
|Метаданные|WS-Policy 1.5|[WS-Policy 1.5](https://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> WCF используется спецификация WS-Policy вместе с доменными утверждениями для описания требований и возможностей служб.|  
|Метаданные|WS-PolicyAttachment|[WS-PolicyAttachment](https://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> В WCF реализована WS-PolicyAttachment для прикрепления выражений политики в различных областях в язык описания веб-служб (WSDL).|  
|Метаданные|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> В WCF реализована WS-MetadataExchange для извлечения схемы XML, WSDL и WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Обмен сообщениями|SOAP 1,1|[SOAP 1.1](https://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> В соответствии со спецификацией Basic Profile 1.1 элемент `basicHttpBinding` реализует протокол обмена сообщениями SOAP 1.1.|  
|Безопасность|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> В соответствии со спецификацией Basic Security Profile элемент `basicHttpBinding` реализует спецификацию Web Services Security (WSS) SOAP Message Security 1.0 для имени пользователя/пароля и безопасности на основе сертификатов X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Безопасность|WSS SOAP Message Security UsernameToken Profile 1.0|[Профиль UsernameToken безопасности сообщения SOAP WSS 1.0](https://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Безопасность|WSS SOAP сообщение безопасности профиль маркера сертификата X.509 1.0|[WSS SOAP сообщение безопасности профиль маркера сертификата X.509 1.0](https://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding и wsDualHttpBinding  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Обмен сообщениями|SOAP 1.2|[Учебник для начинающих](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Структуры системы обмена сообщениями](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Дополнения (включая привязку HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> Привязки `wsHttpBinding`, `ws2007HttpBinding` и `wsDualHttpBinding` реализуют рекомендацию спецификации WS-Addressing консорциума W3C (включение асинхронного обмена сообщениями, корреляции сообщений и механизмов адресации без привязки к конкретному транспортному протоколу).<br /><br /> WCF не поддерживает шифрование заголовков WS-Addressing, хотя это допускается спецификациями WS-*.|  
|Обмен сообщениями|WS-Addressing 1.0 ― метаданные|[Метаданные WS-Addressing 1.0](http://www.w3.org/2007/05/addressing/metadata) поддержка этого протокола включается путем задания версии политики в поведении ServiceMetadata ― policyversion задано значение 1,2 (по умолчанию), описание wsdl соответствует WS-Addressing wsdl, с policyversion задано значение 1,5, описание wsdl соответствует метаданным ws-addressing.<br /><br /> WCF не поддерживает шифрование заголовков WS-Addressing, хотя это допускается спецификациями WS-*.|  
|Безопасность|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> Используется, когда атрибуту `securityMode` присвоено значение "wsSecurityOverHttp" (по умолчанию) и параметры настроены с использованием дочернего элемента `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Безопасность|Профиль UsernameToken безопасности сообщения SOAP WSS 1.1|[Профиль UsernameToken безопасности сообщения SOAP WSS 1.0](https://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> Используется, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Username".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP сообщение безопасности профиль маркера сертификата X.509 1.1](https://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> Используется для защиты сообщений, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Username", "Certificate" или "None". Кроме того, используется для проверки подлинности клиентов, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Certificate".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Message Security Kerberos Token Profile 1.1|[Профиль маркера Kerberos безопасности сообщения SOAP WSS 1.1](https://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> Используется для проверки подлинности и защиты сообщений, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Безопасность|WS-SecureConversation|[WS-SecureConversation](https://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Используется для обеспечения безопасного сеанса, когда атрибуту `security/@mode` присвоено значение "Message", а атрибуту `message/@establishSecurityContext` присвоено значение "true" (по умолчанию).|  
|Безопасность|WS-Trust|[WS-Trust](https://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> Используется в спецификации WS-SecureConversation (см. выше).|  
|Надежный обмен сообщениями|WS-ReliableMessaging|[WS-ReliableMessaging](https://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> Используется, когда привязка настроена на использование свойства `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Транзакции|WS-AtomicTransaction|[WS-AtomicTransaction](https://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> Используется для обмена данными между диспетчерами транзакций. Клиенты и службы WCF всегда используют локальные диспетчеры транзакций.|  
|Транзакции|WS-Coordination|[WS-Coordination](https://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> Используется для поточной передачи контекста транзакций, когда атрибуту присвоено значение `flowTransactions` "Allowed" или "Required".<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding и ws2007FederationHttpBinding  
 [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) и [ \<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) элементы вводятся для обеспечения поддержки федеративных сценариев, где это третий лицо выдает маркер, используемый для проверки подлинности клиента. В дополнение к протоколам, используемым привязкой `wsHttpBinding`, привязка `wsFederationHttpBinding` позволяет использовать следующие спецификации:  
  
-   `WS-Trust` для выдачи маркеров.  
  
-   WSS Security Assertions Markup Language (SAML) Token Profile 1.0 и 1.1 для наиболее часто выдаваемого формата маркеров.  
  
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
  
 Дополнительные сведения см. в разделе [федерации](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>Предоставляемые системой привязки метаданных  
 В следующих таблицах приведены протоколы, поддерживаемые предоставляемыми системой привязками метаданных, которые предоставляются классом <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 [ \<MexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) привязка поддерживает следующие протоколы. Дополнительные сведения об использовании этой привязки см. в разделе [публикация метаданных](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)|  
|Обмен сообщениями|SOAP 1.2|[Учебник для начинающих](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Структуры системы обмена сообщениями](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Дополнения (включая привязку HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|Метаданные|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> В WCF реализована WS-MetadataExchange для извлечения схемы XML, WSDL и WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 [\<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) поддерживает следующие протоколы. Дополнительные сведения об использовании этой привязки см. в разделе [публикация метаданных](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> Безопасность транспорта включена.|  
|Обмен сообщениями|SOAP 1.2|[Учебник для начинающих](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Структуры системы обмена сообщениями](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Дополнения (включая привязку HTTP)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|Метаданные|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> В WCF реализована WS-MetadataExchange для извлечения схемы XML, WSDL и WS-Policy.|  
  
## <a name="see-also"></a>См. также  
 [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)  
 [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)  
 [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)  
 [\<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)  
 [\<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
