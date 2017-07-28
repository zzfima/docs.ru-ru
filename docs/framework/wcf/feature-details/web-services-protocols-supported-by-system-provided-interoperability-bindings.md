---
title: "Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками | Microsoft Docs"
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
  - "протоколы WS"
  - "протоколы веб-служб"
  - "Windows Communication Foundation протоколы веб-служб"
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
caps.latest.revision: 39
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками
Платформа [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предназначена для взаимодействия с веб-службами, поддерживающими набор спецификаций, называемых спецификациями веб-служб. Для упрощения настройки служб взаимодействия рекомендации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] введены три совместимые системные привязки: <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName>, <xref:System.ServiceModel.WSHttpBinding?displayProperty=fullName>, и <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName>. Для обеспечения взаимодействия с организации стандартов продвижения из структурированных сведения стандартов (OASIS) [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предусмотрена одна предоставляемая системой привязка: <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=fullName>. Для публикации метаданных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] включает две совместимые системные привязки: [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) и [ <> \</> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). В этом разделе перечислены спецификации, поддерживаемые предоставляемыми системой привязками с возможностью взаимодействия.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Протоколы веб-служб, поддерживаемые привязками basicHttpBinding, wsHttpBinding, ws2007HttpBinding и wsDualHttpBinding  
  
### <a name="all-bindings"></a>Все привязки  
 The [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), and [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) bindings support the following protocols.  
  
> [!NOTE]
>  Сведения о привязках, используемых для публикации метаданных, см. в разделе "Предоставляемые системой привязки метаданных" ниже.  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`, `WSHttpBinding`, и `WS2007HttpBinding` используют протоколы HTTP и HTTPS.|  
|Обмен сообщениями|MTOM|[MTOM](http://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`, `wsHttpBinding` и `ws2007HttpBinding` поддерживают механизм оптимизации передачи сообщений (MTOM). По умолчанию не используется. Чтобы использовать MTOM, присвойте атрибуту `messageEncoding` значение `"Mtom"`.<br /><br /> Пример<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Метаданные|WSDL 1.1|[WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] язык WSDL используется для описания служб.|  
|Метаданные|WS-Policy|[WS-Policy](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] спецификация WS-Policy используется вместе с доменными утверждениями для описания требований и возможностей служб.|  
|Метаданные|WS-Policy 1.5|[WS-Policy 1.5](http://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] спецификация WS-Policy используется вместе с доменными утверждениями для описания требований и возможностей служб.|  
|Метаданные|WS-PolicyAttachment|[WS-PolicyAttachment](http://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификацию WS-PolicyAttachment для прикрепления выражений политики в различных областях на языке WSDL.|  
|Метаданные|WS-MetadataExchange|[WS-MetadataExchange.](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификацию WS-MetadataExchange для извлечения схемы XML, языка WSDL и спецификации WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Обмен сообщениями|SOAP 1,1|[SOAP 1.1](http://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> В соответствии со спецификацией Basic Profile 1.1 элемент `basicHttpBinding` реализует протокол обмена сообщениями SOAP 1.1.|  
|Безопасность|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> В соответствии со спецификацией Basic Security Profile элемент `basicHttpBinding` реализует спецификацию Web Services Security (WSS) SOAP Message Security 1.0 для имени пользователя/пароля и безопасности на основе сертификатов X.509.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Безопасность|WSS SOAP Message Security UsernameToken Profile 1.0|[WSS SOAP Message Security UsernameToken Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Безопасность|WSS SOAP сообщения безопасности профиль маркера сертификата X.509 1.0|[WSS SOAP сообщения безопасности профиль маркера сертификата X.509 1.0](http://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding и wsDualHttpBinding  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Обмен сообщениями|SOAP 1.2|[Основные сведения о](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Структуры системы обмена сообщениями](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Дополнения (включая привязку HTTP)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> Привязки `wsHttpBinding`, `ws2007HttpBinding` и `wsDualHttpBinding` реализуют рекомендацию спецификации WS-Addressing консорциума W3C (включение асинхронного обмена сообщениями, корреляции сообщений и механизмов адресации без привязки к конкретному транспортному протоколу).<br /><br /> WCF не поддерживает шифрование заголовков WS-Addressing, хотя это допускается спецификациями WS-*.|  
|Обмен сообщениями|WS-Addressing 1.0 ― метаданные|[Метаданные WS-Addressing 1.0](http://www.w3.org/2007/05/addressing/metadata) поддержка этого протокола включается путем задания версии политики в поведении ServiceMetadata -; Если параметру policyversion задано значение 1,2 (по умолчанию), описание wsdl соответствует WS-Addressing wsdl; Если параметру policyversion задано значение 1,5, описание wsdl соответствует метаданным ws-addressing.<br /><br /> WCF не поддерживает шифрование заголовков WS-Addressing, хотя это допускается спецификациями WS-*.|  
|Безопасность|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> Используется, когда атрибуту `securityMode` присвоено значение "wsSecurityOverHttp" (по умолчанию) и параметры настроены с использованием дочернего элемента `wsSecurity`.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Message Security UsernameToken Profile 1.1|[WSS SOAP Message Security UsernameToken Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> Используется, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Username".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP сообщение профиль сертификата X.509 безопасности маркера 1.1](http://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> Используется для защиты сообщений, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Username", "Certificate" или "None". Кроме того, используется для проверки подлинности клиентов, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Certificate".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Безопасность|WSS SOAP Message Security Kerberos Token Profile 1.1|[Профиль маркера Kerberos безопасности сообщения SOAP WSS 1.1](http://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> Используется для проверки подлинности и защиты сообщений, когда атрибуту `wsSecurity` элемента `authenticationMode` присвоено значение "Windows".<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Безопасность|WS-SecureConversation|[WS-SecureConversation](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Используется для обеспечения безопасного сеанса, когда атрибуту `security/@mode` присвоено значение "Message", а атрибуту `message/@establishSecurityContext` присвоено значение "true" (по умолчанию).|  
|Безопасность|WS-Trust|[WS-Trust](http://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> Используется в спецификации WS-SecureConversation (см. выше).|  
|Надежный обмен сообщениями|WS-ReliableMessaging|[WS-ReliableMessaging](http://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> Используется, когда привязка настроена на использование свойства `reliableSession`.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Транзакции|WS-AtomicTransaction|[WS-AtomicTransaction](http://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> Используется для обмена данными между диспетчерами транзакций. Клиенты и службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда используют локальные диспетчеры транзакций.|  
|Транзакции|WS-Coordination|[WS-Coordination](http://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> Используется для поточной передачи контекста транзакций, когда атрибуту присвоено значение `flowTransactions` "Allowed" или "Required".<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding и ws2007FederationHttpBinding  
 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) И [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) элементы, предназначенные для обеспечения поддержки федеративных сценариев, в которых третье лицо выдает маркер, используемый для проверки подлинности клиента. В дополнение к протоколам, используемым привязкой `wsHttpBinding`, привязка `wsFederationHttpBinding` позволяет использовать следующие спецификации:  
  
-   `WS-Trust` для выдачи маркеров.  
  
-   WSS Security Assertions Markup Language (SAML) Token Profile 1.0 и 1.1 для наиболее часто выдаваемого формата маркеров.  
  
 Пример  
  
```  
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
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Федерации](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>Предоставляемые системой привязки метаданных  
 В следующих таблицах описываются протоколы, поддерживаемые привязками системных метаданных, предоставляемых <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=fullName> класса.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) Привязка поддерживает следующие протоколы. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью этой привязки в разделе [публикация метаданных](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)|  
|Обмен сообщениями|SOAP 1.2|[Основные сведения о](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Структуры системы обмена сообщениями](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Дополнения (включая привязку HTTP)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadata|WS-MetadataExchange|[WS-MetadataExchange.](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификацию WS-MetadataExchange для извлечения схемы XML, языка WSDL и спецификации WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)поддерживает следующие протоколы. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью этой привязки в разделе [публикация метаданных](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Категория|Протокол|Спецификация и использование|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> Безопасность транспорта включена.|  
|Обмен сообщениями|SOAP 1.2|[Основные сведения о](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Структуры системы обмена сообщениями](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Дополнения (включая привязку HTTP)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Обмен сообщениями|WS-Addressing 2005/08|[Web Services Addressing 1.0 - Core](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 - SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadata|WS-MetadataExchange|[WS-MetadataExchange.](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификацию WS-MetadataExchange для извлечения схемы XML, языка WSDL и спецификации WS-Policy.|  
  
## <a name="see-also"></a>См. также  
 [Предоставляемые системой привязки](../../../../docs/framework/wcf/system-provided-bindings.md)   
 [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)   
 [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)   
 [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)   
 [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)   
 [<>\>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)