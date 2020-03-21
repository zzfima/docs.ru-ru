---
title: Протоколы транзакций версии 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: a19329b56bb569a04195b38877a42d635996ff1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184377"
---
# <a name="transaction-protocols-version-10"></a>Протоколы транзакций версии 1.0
Windows Communication Foundation (WCF) версия 1 реализует версию 1.0 протоколов WS-Atomic Transaction и WS-Координация. Для получения дополнительной информации о [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)версии 1.1 см.  
  
|Спецификация/документ|Ссылка|  
|-----------------------------|----------|  
|WS-Coordination|<https://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|WS-AtomicTransaction|<https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 Согласно этим спецификациям протоколов, требуется взаимодействие на двух уровнях: между приложениями и между диспетчерами транзакций (см. следующий рисунок). В спецификациях подробно описываются форматы сообщений и обмен сообщениями для обоих уровней взаимодействия. При обмене между приложениями применяются определенные средства обеспечения безопасности, надежности и методы кодирования, как и при обычном обмене в пределах сообщения. Однако для успешного взаимодействия между диспетчерами транзакций требуется соглашение по конкретной привязке, поскольку она обычно не настраивается пользователем.  
  
 В этом разделе описываются состав спецификации протокола WS-Atomic Transaction (WS-AT) со средствами безопасности, а также безопасная привязка, используемая для обмена данными между диспетчерами транзакций. Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination, включая IBM, IONA, Sun Microsystems и пр.  
  
 Следующая цифра изображает совместимость между двумя менеджерами транзакций, менеджером транзакций 1 и менеджером транзакций 2, и двумя приложениями, Приложение 1 и Приложение 2:  
  
 ![Скриншот, отображающие взаимодействие между менеджерами транзакций.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 Рассмотрим типовой сценарий WS-Coordination/WS-Atomic Transaction с одним инициатором (I) и одним участником (P). И инициатор, и участник имеют диспетчеры транзакций (ITM и PTM, соответственно). Двухфазная фиксация обозначается в этом разделе как 2PC.  
  
|||  
|-|-|  
|1. СозданиеКоординацияКонтекст|12. Ответ на сообщение приложения|  
|2. СозданиеКоординационнаяКонтекстОтвет|13. Обязательство (Завершение)|  
|3. Регистрация (Завершение)|14. Подготовка (2PC)|  
|4. РегистрацияОтвет|15. Подготовка (2PC)|  
|5. Сообщение приложения|16. Подготовлено (2PC)|  
|6. СозданиеКоординацияКонтекст с контекстом|17. Подготовлено (2PC)|  
|7. Регистрация (Долговечная)|18. Совершенные (Завершение)|  
|8. РегистрацияОтвет|19. Обязательство (2PC)|  
|9. СозданиеКоординационнаяКонтекстОтвет|20. Обязательство (2PC)|  
|10. Регистрация (Долговечная)|21. Совершенные (2PC)|  
|11. РегистрацияОтвет|22. Совершенные (2PC)|  
  
 В этом документе описываются состав спецификации протокола WS-AtomicTransaction со средствами безопасности, а также безопасная привязка, используемая для взаимодействия между диспетчерами транзакций. Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination.  
  
 На рисунке и в таблице представлены четыре класса сообщений с точки зрения безопасности:  
  
- сообщения активации (CreateCoordinationContext и CreateCoordinationContextResponse);  
  
- сообщения регистрации (Register и RegisterResponse);  
  
- протокольные сообщения (Prepare, Rollback, Commit, Aborted и т. д.);  
  
- сообщения приложений.  
  
 Первые три класса сообщений считаются сообщениями диспетчера транзакций и их конфигурация привязки описывается в разделе "Обмен сообщениями приложений" ниже в данном разделе. Четвертый класс сообщений - это сообщения, передаваемые между приложениями, которые описываются в разделе "Примеры сообщений" ниже в данном разделе. В этом разделе описаны протокольные привязки, используемые для каждого из этих классов WCF.  
  
 Во всем данном документе используются следующие пространства имен XML и связанные с ними префиксы.  
  
|Prefix|Универсальный код ресурса (URI) пространства имен|  
|------------|-------------------|  
|s11|http://schemas.xmlsoap.org/soap/envelope|  
|wsa|http://www.w3.org/2004/08/addressing|  
|wscoor|http://schemas.xmlsoap.org/ws/2004/10/wscoor|  
|wsat|http://schemas.xmlsoap.org/ws/2004/10/wsat|  
|t|http://schemas.xmlsoap.org/ws/2005/02/trust|  
|o|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd|  
|xsd|http://www.w3.org/2001/XMLSchema|  
  
## <a name="transaction-manager-bindings"></a>Привязки диспетчеров транзакций  
 R1001: для обмена сообщениями протоколов WS-Atomic Transaction и WS-Coordination диспетчеры транзакций должны использовать SOAP 1.1 и WS-Addressing 2004/08.  
  
 Сообщения приложений не ограничиваются этими привязками и описываются ниже.  
  
### <a name="transaction-manager-https-binding"></a>Привязка HTTPS диспетчера транзакций  
 Для обеспечения безопасности и установления доверия между каждой парой "отправитель-получатель" в дереве транзакций привязка HTTPS диспетчера транзакций полагается только на механизм безопасности транспорта.  
  
#### <a name="https-transport-configuration"></a>Конфигурация транспорта HTTPS  
 Сертификаты X.509 используются для установления идентификации диспетчера транзакций. Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации:  
  
- R1111: сертификаты X.509, представляемые по линии связи, должны иметь имя субъекта, соответствующее полному доменному имени исходного компьютера;  
  
- B1112: для успешного выполнения проверок имени субъекта X.509 между каждой парой "отправитель-получатель" в системе должна работать служба DNS.  
  
#### <a name="activation-and-registration-binding-configuration"></a>Конфигурация привязки активации и регистрации  
 WCF требует привязки дуплекса запроса/ответа с корреляцией по HTTPS. (Дополнительные сведения о корреляции и описание шаблонов обмена сообщениями "запрос-ответ" см. в разделе 8 спецификации WS-Atomic Transaction.)  
  
#### <a name="2pc-protocol-binding-configuration"></a>Конфигурация привязки протокола 2PC  
 WCF поддерживает односторонние (данные) сообщения через HTTPS. Корреляция между сообщениями зависит от реализации.  
  
 B2131: Реализация должна `wsa:ReferenceParameters` поддерживаться, как описано в WS-Addressing для достижения корреляции 2PC сообщений WCF.  
  
### <a name="transaction-manager-mixed-security-binding"></a>Привязка безопасности диспетчера транзакций смешанного режима  
 Это альтернативный (смешанный режим) привязка, который использует транспортную безопасность в сочетании с моделью WS-Координация выпущенных токенов для целей создания идентификационных данных.  В двух привязках отличаются только элементы "Активация" и "Регистрация".  
  
#### <a name="https-transport-configuration"></a>Конфигурация транспорта HTTPS  
 Сертификаты X.509 используются для установления идентификации диспетчера транзакций. Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации.  
  
#### <a name="activation-message-binding-configuration"></a>Конфигурация привязки сообщений активации  
 Сообщения активации обычно не участвуют во взаимодействии, поскольку они, как правило, передаются между приложением и его локальным диспетчером транзакций.  
  
 B1221: WCF использует дуплексную привязку HTTPS (описанную в [протоколах обмена сообщениями)](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)для сообщений активации. Сообщения запроса и ответа коррелируются с помощью WS-Addressing 2004/08.  
  
 В разделе 8 спецификации WS-Atomic Transaction приводятся дополнительные сведения о корреляции и шаблонах обмена сообщениями.  
  
- R1222: при получении сообщения `CreateCoordinationContext` координатор должен выдать маркер `SecurityContextToken` со связанным с ним паролем `STx`. Этот маркер возвращается в заголовке `t:IssuedTokens` согласно спецификации WS-Trust.  
  
- R1223: если активация происходит в пределах существующего контекста координации, в сообщении `t:IssuedTokens` должен передаваться заголовок `SecurityContextToken` с маркером `CreateCoordinationContext`, связанным с существующим контекстом.  
  
 Для `t:IssuedTokens` присоединения к исходящего `wscoor:CreateCoordinationContextResponse` сообщению должен быть создан новый заголовок.  
  
#### <a name="registration-message-binding-configuration"></a>Конфигурация привязки сообщений регистрации  
 B1231: WCF использует дуплексную привязку HTTPS (описано в [протоколах обмена сообщениями).](../../../../docs/framework/wcf/feature-details/messaging-protocols.md) Сообщения запроса и ответа коррелируются с помощью WS-Addressing 2004/08.  
  
 В разделе 8 спецификации WS-AtomicTransaction приводятся дополнительные сведения о корреляции и описание шаблонов обмена сообщениями.  
  
 R1232: Исходящие `wscoor:Register` сообщения `IssuedTokenOverTransport` должны использовать режим проверки подлинности, описанный в [Протоколах безопасности.](../../../../docs/framework/wcf/feature-details/security-protocols.md)  
  
 Элемент `wsse:Timestamp` должен быть подписан `SecurityContextToken STx` с помощью выданного. Эта подпись является доказательством владения маркером, связанным с конкретной транзакцией, и используется для проверки подлинности зачисления участника в транзакцию. Сообщение RegistrationResponse отправляется обратно по протоколу HTTPS.  
  
#### <a name="2pc-protocol-binding-configuration"></a>Конфигурация привязки протокола 2PC  
 WCF поддерживает односторонние (данные) сообщения через HTTPS. Корреляция между сообщениями зависит от реализации.  
  
 B2131: Реализация должна `wsa:ReferenceParameters` поддерживаться, как описано в WS-Addressing для достижения корреляции 2PC сообщений WCF.  
  
## <a name="application-message-exchange"></a>Обмен сообщениями приложений  
 Для сообщений, передаваемых между приложениями, приложения могут использовать любую привязку, если она удовлетворяет следующим требованиям безопасности.  
  
- R2001: заголовок сообщений, передаваемых между приложениями, должен содержать заголовок `t:IssuedTokens` наряду с `CoordinationContext`.  
  
- R2002: необходимо обеспечение целостности и конфиденциальности `t:IssuedToken`.  
  
 Заголовок `CoordinationContext` содержит `wscoor:Identifier`. В то `xsd:AnyURI` время как определение позволяет использовать как абсолютные, так и относительные URI, WCF поддерживает только, `wscoor:Identifiers`которые являются абсолютными URIs.  
  
 `wscoor:Identifier` Если `wscoor:CoordinationContext` является относительным URI, неисправности будут возвращены из транзакционных служб WCF.  
  
## <a name="message-examples"></a>Примеры сообщений  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a>Сообщения запроса и ответа CreateCoordinationContext  
 Следующие сообщения соответствуют шаблону "запрос-ответ".  
  
#### <a name="createcoordinationcontext"></a>CreateCoordinationContext  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a>CreateCoordinationContextResponse  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a>Сообщения регистрации  
 Следующие сообщения являются сообщениями регистрации.  
  
#### <a name="register"></a>Зарегистрировать  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a>Register Response  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a>Сообщения протокола двухфазной фиксации  
 Следующее сообщение относится к протоколу двухфазной фиксации (2PC).  
  
#### <a name="commit"></a>Commit  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a>Сообщения приложений  
 Следующие сообщения являются сообщениями приложений.  
  
#### <a name="application-message-request"></a>Сообщение приложения - запрос  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken
          wssu:Id="IA_Certificate"
          ValueType="...#X509v3"
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->
    <e:EncryptedData Id="encrypted_body"
           Type="http://www.w3.org/2001/04/xmlenc#Content"
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
