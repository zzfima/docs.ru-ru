---
title: "Руководство по взаимодействию по протоколам веб-служб | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Руководство по взаимодействию по протоколам веб-служб
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] реализует ряд протоколов веб\-служб.  Многие из этих протоколов предусматривают ряд параметров и точек расширяемости, оставляемых на усмотрение реализующего субъекта.  В этом подразделе приводится список протоколов веб\-служб, реализуемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  В остальных подразделах содержатся подробности о реализации каждого поддерживаемого протокола.  
  
## Протоколы веб\-служб, реализуемые WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает поддержку протоколов инфраструктуры веб\-служб \(Web services, WS\), в том числе протоколов каналов и протоколов приложений веб\-служб, посредством контрактов.  Взаимодействие для протоколов приложений обеспечивается посредством языка описания схемы XML \(XSD\) 1.0 и языка описания веб\-служб \(WSDL\) 1.1.  
  
 Взаимодействие протоколов инфраструктуры обеспечивается спецификациями WS\-\*.  Каналы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивают поддержку ряда протоколов инфраструктуры WS\-\*.  Для настройки каналов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используются элементы привязки.  В приведенных ниже таблицах содержится полный перечень протоколов инфраструктуры WS\-\*, реализуемых различными элементами привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Элемент привязки <xref:System.ServiceModel.Channels.HttpTransportBindingElement> поддерживает спецификации, приведенные в следующей таблице.  
  
|Спецификация\/документ|Ссылка|  
|----------------------------|------------|  
|HTTP 1.1|[RFC 2616](http://go.microsoft.com/fwlink/?LinkID=90372)|  
|Привязка SOAP 1.1 HTTP|[Протокол SOAP 1.1](http://go.microsoft.com/fwlink/?LinkId=90520), раздел 7|  
|Привязка SOAP 1,2 HTTP|[Протокол SOAP, версия 1.2, часть 2: Дополнения \(второе издание\)](http://go.microsoft.com/fwlink/?LinkId=95329), раздел 7|  
  
 Элементы привязки <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> и <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> поддерживают спецификации, приведенные в следующей таблице.  
  
|Спецификация\/документ|Ссылка|  
|----------------------------|------------|  
|XML|[Язык XML 1.0 \(четвертый выпуск\)](http://go.microsoft.com/fwlink/?LinkId=15139)|  
|SOAP 1,1|[Протокол SOAP 1.1](http://go.microsoft.com/fwlink/?LinkId=96687)|  
|SOAP 1.2 Core|[Протокол SOAP, версия 1.2, часть 1: Платформа обмена сообщениями \(второе издание\)](http://go.microsoft.com/fwlink/?LinkId=94664)|  
|WS\-Addressing 2004\/08|[Адресация веб\-служб \(WS\-Addressing\)](http://go.microsoft.com/fwlink/?LinkId=81239)|  
|W3C Web Services Addressing 1.0 \- Core|[Адресация веб\-служб 1.0 — Ядро](http://go.microsoft.com/fwlink/?LinkId=96688)|  
|W3C Web Services Addressing 1.0 \- привязка SOAP|[Адресация веб\-служб 1.0 — Привязка SOAP](http://go.microsoft.com/fwlink/?LinkId=96689)|  
|W3C Web Services Addressing 1.0 \- привязка WSDL\*|[Адресация веб\-служб 1.0 — Привязка WSDL](http://go.microsoft.com/fwlink/?LinkId=96690)|  
|W3C Web Services Addressing 1.0 \- метаданные|[Адресация веб\-служб 1.0 — Метаданные](http://www.w3.org/TR/ws-addr-metadata/)|  
|Привязка WSDL SOAP1.1|[Язык описания веб\-служб \(WSDL\) 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)|  
|Привязка WSDL SOAP1.2|[Расширение привязки WSDL 1.1 для протокола SOAP 1.2](http://go.microsoft.com/fwlink/?LinkId=96691)|  
  
 Элемент привязки <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> поддерживает спецификации, приведенные в следующей таблице.  
  
|Спецификация\/документ|Ссылка|  
|----------------------------|------------|  
|XOP|[Оптимизированная упаковка двоичных данных XML](http://go.microsoft.com/fwlink/?LinkId=96714)|  
|MTOM \+ привязка SOAP1.2|[Механизм оптимизации передачи сообщений SOAP](http://go.microsoft.com/fwlink/?LinkId=96713)|  
|Привязка MTOM SOAP 1.1|[Привязка SOAP 1.1 для MTOM 1.0](http://go.microsoft.com/fwlink/?LinkId=96712)|  
|MTOM WS\-PolicyAssertions|Готовится к публикации.|  
  
 Элемент привязки <xref:System.ServiceModel.Channels.SecurityBindingElement> поддерживает спецификации, приведенные в следующей таблице.  
  
|Спецификация\/документ|Ссылка|  
|----------------------------|------------|  
|WSS: SOAP Message Security 1,0|[Безопасность веб\-служб: безопасность передачи сообщений SOAP 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)|  
|WSS: Username Token Profile 1.0|[Профиль UsernameToken безопасности веб\-служб 1.0](http://go.microsoft.com/fwlink/?LinkId=95334).<br /><br /> требуется Password\/@Type\=PasswordText \(default\)|  
|WSS: X.509 Token Profile 1.0|[Профиль маркера сертификата X.509 безопасности веб\-служб](http://go.microsoft.com/fwlink/?LinkId=95335).|  
|WSS: SAML 1.1 Token Profile 1,0|[Безопасность веб\-служб: профиль маркера SAML](http://go.microsoft.com/fwlink/?LinkId=96693)|  
|WSS: SOAP Message Security 1.1|[Безопасность веб\-служб: безопасность передачи сообщений SOAP 1.1](http://go.microsoft.com/fwlink/?LinkId=91240)|  
|WSS Username Token Profile 1.1|[Профиль UsernameToken безопасности веб\-служб 1.1](http://go.microsoft.com/fwlink/?LinkId=95331).<br /><br /> не реализуется получение производного ключа на основе пароля;<br /><br /> требуется Password\/@Type\=PasswordText \(default\)|  
|WSS: X509 Token Profile 1.1|[Профиль маркера сертификата X.509 безопасности веб\-служб 1.1](http://go.microsoft.com/fwlink/?LinkId=95332).|  
|WSS: Kerberos Token Profile 1.1|[Профиль маркера Kerberos безопасности веб\-служб 1.1](http://go.microsoft.com/fwlink/?LinkId=95333).|  
|WSS: SAML 1.1 Token Profile 1.1|[Профиль маркера SAML безопасности веб\-служб 1.1](http://go.microsoft.com/fwlink/?LinkId=96694)|  
|WS\-Secure Conversation|[Web Services Secure Conversation Language](http://go.microsoft.com/fwlink/?LinkId=95317)|  
|WS\-Trust 1.4|[Web Services Trust Language](http://go.microsoft.com/fwlink/?LinkId=169514)|  
|WS\-SecurityPolicy 2005\/07|[Web Services Secure Conversation Language](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> \(С учетом списка ошибок, переданных в технический комитет OASIS WS\-SX.\)<br /><br /> [Сообщение ws\-sx](http://go.microsoft.com/fwlink/?LinkId=96700)|  
|WS\-ReliableMessaging 1.1|[Протокол надежного обмена сообщениями, версия 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)|  
  
 Элемент привязки <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> поддерживает спецификации, приведенные в следующей таблице.  
  
|Спецификация\/документ|Ссылка|  
|----------------------------|------------|  
|WS\-Coordination|[Web Services Coordination](http://go.microsoft.com/fwlink/?LinkId=95324)|  
|WS\-AtomicTransaction|[Web Services Atomic Transaction](http://go.microsoft.com/fwlink/?LinkId=95323)|  
  
 Классы <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WSDLExporter>, <xref:System.ServiceModel.Description.WSDLImporter> и <xref:System.ServiceModel.Description.MetadataResolver> обеспечивают поддержку следующих спецификаций метаданных.  
  
-   [Схема XML, часть 1: Структуры \(второе издание\)](http://go.microsoft.com/fwlink/?LinkId=3536)  
  
-   [Схема XML, часть 2: Типы данных \(второе издание\)](http://go.microsoft.com/fwlink/?LinkId=40138)  
  
-   [WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)  
  
-   [WS\-Policy 1.2](http://go.microsoft.com/fwlink/?LinkId=96705)  
  
-   [WS\-Policy 1.5](http://go.microsoft.com/fwlink/?LinkId=96706)  
  
-   [WS\-PolicyAttachment 1.2](http://go.microsoft.com/fwlink/?LinkId=96707)  
  
-   [WS\-MetadataExchange 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)  
  
-   [WS\-Transfer Get для извлечения метаданных](http://go.microsoft.com/fwlink/?LinkId=96708)  
  
 Кроме того, в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализованы следующие профили взаимодействия:  
  
-   [Basic Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=69313)  
  
-   [Простая привязка SOAP 1.0](http://go.microsoft.com/fwlink/?LinkId=96710)  
  
-   [Рабочий проект профиля Basic Security Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=96711)  
  
## См. также  
 [Протоколы веб\-служб, поддерживаемые предоставляемыми системой привязками](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)   
 [Протоколы обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)   
 [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)   
 [WSDL и политика](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)   
 [Протоколы безопасности](../../../../docs/framework/wcf/feature-details/security-protocols.md)   
 [Протокол надежного обмена сообщениями, версия 1.0](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-0.md)   
 [Протокол надежного обмена сообщениями, версия 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)   
 [Протоколы транзакций](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)   
 [Протокол обмена контекстом](../../../../docs/framework/wcf/feature-details/context-exchange-protocol.md)