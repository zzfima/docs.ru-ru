---
title: Рекомендации по взаимодействию протоколов веб-служб
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 1b949880b3ebbaf121b79a958d17cf5708affcf3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636150"
---
# <a name="web-services-protocols-interoperability-guide"></a>Рекомендации по взаимодействию протоколов веб-служб

Windows Communication Foundation (WCF) реализует ряд протоколов веб-служб. Многие из этих протоколов предусматривают ряд параметров и точек расширяемости, оставляемых на усмотрение реализующего субъекта. В этом разделе содержится список протоколов веб-служб, реализованных в WCF. В остальных подразделах содержатся подробности о реализации каждого поддерживаемого протокола.

## <a name="web-services-protocols-implemented-by-wcf"></a>Протоколы веб-служб, реализованные WCF

WCF обеспечивает поддержку протоколов инфраструктуры веб-служб (WS) через каналы и протоколы приложений веб-служб с помощью функций контрактов. Взаимодействие для протоколов приложений обеспечивается посредством языка описания схемы XML (XSD) 1.0 и языка описания веб-служб (WSDL) 1.1.

Взаимодействие протоколов инфраструктуры обеспечивается спецификациями WS-*. Каналы WCF обеспечивают поддержку нескольких протоколов инфраструктуры WS-\*. Каналы WCF настраиваются с помощью элементов привязки. В следующих таблицах содержится полный список протоколов инфраструктуры WS-\*, реализованных различными элементами привязки WCF.

Элемент привязки <xref:System.ServiceModel.Channels.HttpTransportBindingElement> поддерживает спецификации, приведенные в следующей таблице.

|Спецификация/документ|Ссылка|
|-----------------------------|----------|
|HTTP 1.1|[RFC 2616](https://www.rfc-editor.org/rfc/rfc2616.txt)|
|Привязка SOAP 1.1 HTTP|[Протокол SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), раздел 7|
|Привязка SOAP 1,2 HTTP|[SOAP версии 1,2, часть 2: дополнения (второй выпуск)](https://www.w3.org/TR/soap12-part2/), раздел 7|

Элементы привязки <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> и <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> поддерживают спецификации, приведенные в следующей таблице.

|Спецификация/документ|Ссылка|
|-----------------------------|----------|
|XML|[Язык XML (XML) 1,0 (Четвертый выпуск)](https://www.w3.org/TR/REC-xml/)|
|SOAP 1,1|[Протокол SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)|
|SOAP 1.2 Core|[SOAP версии 1,2, часть 1. платформа обмена сообщениями (второй выпуск)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)|
|WS-Addressing 2004/08|[Адресация веб-служб (WS-Addressing)](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)|
|W3C Web Services Addressing 1.0 - Core|[Адресация веб-служб 1,0-Core](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509/)|
|W3C Web Services Addressing 1.0 - привязка SOAP|[Адресация веб-служб 1,0 — SOAP-привязка](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509/)|
|W3C Web Services Addressing 1.0 - привязка WSDL*|[Обращение к веб-службам 1,0 — привязка WSDL](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)|
|W3C Web Services Addressing 1.0 - метаданные|[Адресация веб-служб 1,0-метаданные](https://www.w3.org/TR/ws-addr-metadata/)|
|Привязка WSDL SOAP1.1|[Язык описания веб-служб (WSDL) 1,1](https://www.w3.org/TR/wsdl/)|
|Привязка WSDL SOAP1.2|[Расширение привязки WSDL 1,1 для SOAP 1,2](https://www.w3.org/Submission/wsdl11soap12/)|

Элемент привязки <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> поддерживает спецификации, приведенные в следующей таблице.

|Спецификация/документ|Ссылка|
|-----------------------------|----------|
|XOP|[XML — оптимизированная двоичная упаковка](https://www.w3.org/TR/xop10/)|
|MTOM + привязка SOAP1.2|[Механизм оптимизации передачи сообщений SOAP](https://www.w3.org/TR/soap12-mtom/)|
|Привязка MTOM SOAP 1.1|[Привязка SOAP 1,1 к MTOM 1,0](https://www.w3.org/Submission/soap11mtom10/)|
|MTOM WS-PolicyAssertions|[Утверждение политики сериализации MTOM (WS-Мтомполици)](https://www.w3.org/Submission/WS-MTOMPolicy/)|

Элемент привязки <xref:System.ServiceModel.Channels.SecurityBindingElement> поддерживает спецификации, приведенные в следующей таблице.

|Спецификация/документ|Ссылка|
|-----------------------------|----------|
|WSS: SOAP Message Security 1,0|[WS-Security: безопасность сообщений SOAP 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)|
|WSS: Username Token Profile 1.0|[WS-Security UsernameToken профиль 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> требовать Password/@Type= Пассвордтекст (по умолчанию)|
|WSS: X.509 Token Profile 1.0|[Профиль маркера сертификата WS-Security X. 509](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)|
|WSS: SAML 1.1 Token Profile 1,0|[WS-Security: профиль токена SAML](https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf)|
|WSS: SOAP Message Security 1.1|[WS-Security: безопасность сообщений SOAP 1,1](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf)|
|WSS Username Token Profile 1.1|[WS-Security UsernameToken профиль 1,1](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> не реализуется получение производного ключа на основе пароля;<br /><br /> требовать Password/@Type= Пассвордтекст (по умолчанию)|
|WSS: X509 Token Profile 1.1|[WS-Security X. 509. профиль маркера сертификата 1,1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)|
|WSS: Kerberos Token Profile 1.1|[WS-Security профиля токена Kerberos 1,1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)|
|WSS: SAML 1.1 Token Profile 1.1|[WS-Security профиля токена SAML 1,1](https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf)|
|WS-Secure Conversation|[Язык защищенного диалога веб-служб](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)|
|WS-Trust 1.4|[Язык доверия веб-служб](https://docs.oasis-open.org/ws-sx/ws-trust/200802)|
|WS-SecurityPolicy 2005/07|[Язык защищенного диалога веб-служб](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> (С учетом списка ошибок, переданных в технический комитет OASIS WS-SX.)<br /><br /> [сообщение WS-SX](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html)|
|WS-ReliableMessaging 1.1|[Протокол надежного обмена сообщениями версии 1.1](reliable-messaging-protocol-version-1-1.md)|

Элемент привязки <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> поддерживает спецификации, приведенные в следующей таблице.

|Спецификация/документ|Ссылка|
|-----------------------------|----------|
|WS-Coordination|[Координация веб-служб](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))|
|WS-AtomicTransaction|[Атомарная транзакция веб-служб](https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)|

Классы <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> и <xref:System.ServiceModel.Description.MetadataResolver> обеспечивают поддержку следующих спецификаций метаданных.

- [Схема XML, часть 1. Вторая редакция структур](https://www.w3.org/TR/xmlschema-1/)

- [Схема XML, часть 2. тип данных Second Edition](https://www.w3.org/TR/xmlschema-2/)

- [WSDL 1,1](https://www.w3.org/TR/wsdl/)

- [WS-Policy 1,2](https://www.w3.org/Submission/2006/SUBM-WS-Policy-20060425/)

- [WS-Policy 1,5](https://www.w3.org/TR/ws-policy/)

- [WS-Полициаттачмент 1,2](https://www.w3.org/Submission/2006/SUBM-WS-PolicyAttachment-20060425/)

- [WS-MetadataExchange 1,1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)

- [WS-передача Get для получения метаданных](https://www.w3.org/Submission/2006/SUBM-WS-Transfer-20060315/)

Кроме того, следующие профили взаимодействия реализуются в WCF:

- [Базовый профиль 1,1](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html)

- [Простая привязка SOAP 1,0](http://www.ws-i.org/Profiles/SimpleSoapBindingProfile-1.0-2004-08-24.html)

- [Основной профиль безопасности 1,0 рабочий черновик](http://www.ws-i.org/Profiles/BasicSecurityProfile-1.0-2006-03-29.html)

## <a name="see-also"></a>См. также:

- [Протоколы веб-служб, поддерживаемые предоставляемыми системой привязками](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [Протоколы обмена сообщениями](messaging-protocols.md)
- [Справочник по схеме контрактов данных](data-contract-schema-reference.md)
- [WSDL и политика](wsdl-and-policy.md)
- [Протоколы безопасности](security-protocols.md)
- [Протокол надежного обмена сообщениями версии 1.0](reliable-messaging-protocol-version-1-0.md)
- [Протокол надежного обмена сообщениями версии 1.1](reliable-messaging-protocol-version-1-1.md)
- [Протоколы транзакций](transaction-protocols.md)
- [Протокол обмена контекстом](context-exchange-protocol.md)
