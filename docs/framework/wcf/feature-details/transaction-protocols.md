---
title: "Протоколы транзакций | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Протоколы транзакций
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] реализует протоколы WS\-Atomic Transaction и WS\-Coordination.  
  
|Спецификация\/документ|Версия|Ссылка|  
|----------------------------|------------|------------|  
|WS\-Coordination|1.0<br /><br /> 1.1|[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96104](http://go.microsoft.com/fwlink/?LinkId=96104)<br /><br /> [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96079](http://go.microsoft.com/fwlink/?LinkId=96079)|  
|WS\-AtomicTransaction|1.0<br /><br /> 1.1|[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96080](http://go.microsoft.com/fwlink/?LinkId=96080)<br /><br /> http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96081|  
  
 Согласно этим спецификациям протоколов, требуется взаимодействие на двух уровнях: между приложениями и между диспетчерами транзакций \(см. следующий рисунок\).В спецификациях подробно описываются форматы сообщений и обмен сообщениями для обоих уровней взаимодействия.При обмене между приложениями применяются определенные средства обеспечения безопасности, надежности и методы кодирования, как и при обычном обмене в пределах сообщения.Однако для успешного взаимодействия между диспетчерами транзакций требуется соглашение по конкретной привязке, поскольку она обычно не настраивается пользователем.  
  
 В этом разделе описываются состав спецификации протокола WS\-Atomic Transaction \(WS\-AT\) со средствами безопасности, а также безопасная привязка, используемая для обмена данными между диспетчерами транзакций.Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS\-AT и WS\-Coordination, включая IBM, IONA, Sun Microsystems и пр.  
  
 На следующем рисунке показано взаимодействие между двумя диспетчерами транзакций \(диспетчером транзакций 1 и диспетчером транзакций 2\) и двумя приложениями \(приложением 1 и приложением 2\).  
  
 ![Протоколы транзакций](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "TransactionManagers")  
  
 Рассмотрим типовой сценарий WS\-Coordination\/WS\-Atomic Transaction с одним инициатором \(I\) и одним участником \(P\).И инициатор, и участник имеют диспетчеры транзакций \(ITM и PTM, соответственно\).Двухфазная фиксация обозначается в этом разделе как 2PC.  
  
|||  
|-|-|  
|1.CreateCoordinationContext|12.Ответ на сообщение приложения|  
|2.CreateCoordinationContextResponse|13.Commit \(завершение\)|  
|3.Register \(завершение\)|14.Prepare \(2PC\)|  
|4.RegisterResponse|15.Prepare \(2PC\)|  
|5.Сообщение приложения|16.Prepared \(2PC\)|  
|6.CreateCoordinationContext с контекстом|17.Prepared \(2PC\)|  
|7.Register \(устойчивое\)|18.Committed \(завершение\)|  
|8.RegisterResponse|19.Commit \(2PC\)|  
|9.CreateCoordinationContextResponse|20.Commit \(2PC\)|  
|10.Register \(устойчивое\)|21.Committed \(2PC\)|  
|11.RegisterResponse|22.Committed \(2PC\)|  
  
 В этом документе описываются состав спецификации протокола WS\-AtomicTransaction со средствами безопасности, а также безопасная привязка, используемая для взаимодействия между диспетчерами транзакций.Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS\-AT и WS\-Coordination.  
  
 На рисунке и в таблице представлены четыре класса сообщений с точки зрения безопасности:  
  
-   сообщения активации \(CreateCoordinationContext и CreateCoordinationContextResponse\);  
  
-   сообщения регистрации \(Register и RegisterResponse\);  
  
-   протокольные сообщения \(Prepare, Rollback, Commit, Aborted и т. д.\);  
  
-   сообщения приложений.  
  
 Первые три класса сообщений считаются сообщениями диспетчера транзакций и их конфигурация привязки описывается в разделе "Обмен сообщениями приложений" ниже в данном разделе.Четвертый класс сообщений — это сообщения, передаваемые между приложениями, которые описываются в разделе "Примеры сообщений" ниже в данном разделе.В этом разделе описываются привязки протокола, используемые системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для каждого из этих классов.  
  
 Во всем данном документе используются следующие пространства имен XML и связанные с ними префиксы.  
  
|Префикс|Версия|Универсальный код ресурса \(URI\) пространства имен|  
|-------------|------------|---------------------------------------------------------|  
|s11||[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96014](http://go.microsoft.com/fwlink/?LinkId=96014)|  
|wsa|До 1.0<br /><br /> 1.0|http:\/\/www.w3.org\/2004\/08\/addressing<br /><br /> [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96022](http://go.microsoft.com/fwlink/?LinkId=96022)|  
|wscoor|1.0<br /><br /> 1.1|[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96078](http://go.microsoft.com/fwlink/?LinkId=96078)<br /><br /> [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96079](http://go.microsoft.com/fwlink/?LinkId=96079)|  
|wsat|1.0<br /><br /> 1.1|[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96080](http://go.microsoft.com/fwlink/?LinkId=96080)<br /><br /> [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96081](http://go.microsoft.com/fwlink/?LinkId=96081)|  
|t|До 1.3<br /><br /> 1.3|[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96082](http://go.microsoft.com/fwlink/?LinkId=96082)<br /><br /> [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96100](http://go.microsoft.com/fwlink/?LinkId=96100)|  
|o||[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96101](http://go.microsoft.com/fwlink/?LinkId=96101)|  
|xsd||[http:\/\/go.microsoft.com\/fwlink\/?LinkId\=96102](http://go.microsoft.com/fwlink/?LinkId=96102)|  
  
## Привязки диспетчеров транзакций  
 R1001: для обмена сообщениями протоколов WS\-Atomic Transaction и WS\-Coordination диспетчеры транзакций, участвующие в транзакции по протоколу WS\-AT 1.0, должны использовать SOAP 1.1 и WS\-Addressing 2004\/08.  
  
 R1002: для обмена сообщениями протоколов WS\-Atomic Transaction и WS\-Coordination диспетчеры транзакций, участвующие в транзакции по протоколу WS\-AT 1.1, должны использовать SOAP 1.1 и WS\-Addressing 2005\/08.  
  
 Сообщения приложений не ограничиваются этими привязками и описываются ниже.  
  
### Привязка HTTPS диспетчера транзакций  
 Для обеспечения безопасности и установления доверия между каждой парой "отправитель\-получатель" в дереве транзакций привязка HTTPS диспетчера транзакций полагается только на механизм безопасности транспорта.  
  
#### Конфигурация транспорта HTTPS  
 Для установления идентификации диспетчера транзакций используются сертификаты X.509.Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации:  
  
-   R1111: сертификаты X.509, представляемые по линии связи, должны иметь имя субъекта, соответствующее полному доменному имени исходного компьютера;  
  
-   B1112: для успешного выполнения проверок имени субъекта X.509 между каждой парой "отправитель\-получатель" в системе должна работать служба DNS.  
  
#### Конфигурация привязки активации и регистрации  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует дуплексной привязки "запрос\-ответ" с корреляцией по протоколу HTTPS.\(Дополнительные сведения о корреляции и описание шаблонов обмена сообщениями "запрос\-ответ" см. в разделе 8 спецификации WS\-Atomic Transaction.\)  
  
#### Конфигурация привязки протокола 2PC  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает однонаправленную \(датаграммную\) передачу сообщений по протоколу HTTPS.Корреляция между сообщениями зависит от реализации.  
  
 B1131: для обеспечения корреляции сообщений 2PC [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализации должны поддерживать `wsa:ReferenceParameters`, как описано в спецификации WS\-Addressing.  
  
### Привязка безопасности диспетчера транзакций смешанного режима  
 Это альтернативная привязка \(смешанного режима\), которая для установления идентификации использует механизм безопасности транспорта в сочетании с моделью маркера, выдаваемого протоколом WS\-Coordination.В двух привязках отличаются только элементы "Активация" и "Регистрация".  
  
#### Конфигурация транспорта HTTPS  
 Для установления идентификации диспетчера транзакций используются сертификаты X.509.Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации.  
  
#### Конфигурация привязки сообщений активации  
 Сообщения активации обычно не участвуют во взаимодействии, поскольку они, как правило, передаются между приложением и его локальным диспетчером транзакций.  
  
 B1221: для сообщений активации система [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует дуплексную привязку HTTPS \(описанную в разделе [Протоколы обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)\).Сообщения запроса и ответа коррелируются с использованием протокола WS\-Addressing 2004\/08 в случае WS\-AT 1.0 и протокола WS\-Addressing 2005\/08 в случае WS\-AT 1.1.  
  
 В разделе 8 спецификации WS\-Atomic Transaction приводятся дополнительные сведения о корреляции и шаблонах обмена сообщениями.  
  
-   R1222: при получении сообщения `CreateCoordinationContext` координатор должен выдать маркер `SecurityContextToken` со связанным с ним паролем `STx`.Этот маркер возвращается в заголовке `t:IssuedTokens` согласно спецификации WS\-Trust.  
  
-   R1223: если активация происходит в пределах существующего контекста координации, в сообщении `CreateCoordinationContext` должен передаваться заголовок `t:IssuedTokens` с маркером `SecurityContextToken`, связанным с существующим контекстом.  
  
 Для присоединения к исходящему сообщению `wscoor:CreateCoordinationContextResponse` должен формироваться новый заголовок `t:IssuedTokens`.  
  
#### Конфигурация привязки сообщений регистрации  
 B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует дуплексную привязку HTTPS \(описанную в разделе [Протоколы обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)\).Сообщения запроса и ответа коррелируются с использованием протокола WS\-Addressing 2004\/08 в случае WS\-AT 1.0 и протокола WS\-Addressing 2005\/08 в случае WS\-AT 1.1.  
  
 В разделе 8 спецификации WS\-AtomicTransaction приводятся дополнительные сведения о корреляции и описание шаблонов обмена сообщениями.  
  
 R1232: для исходящих сообщений `wscoor:Register` должен использоваться режим проверки подлинности `IssuedTokenOverTransport`, описанный в разделе [Протоколы безопасности](../../../../docs/framework/wcf/feature-details/security-protocols.md).  
  
 Элемент `wsse:Timestamp` должен быть подписан с помощью выданного пароля `STx` маркера `SecurityContextToken`.Эта подпись является доказательством владения маркером, связанным с конкретной транзакцией, и используется для проверки подлинности зачисления участника в транзакцию.Сообщение RegistrationResponse отправляется обратно по протоколу HTTPS.  
  
#### Конфигурация привязки протокола 2PC  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает однонаправленную \(датаграммную\) передачу сообщений по протоколу HTTPS.Корреляция между сообщениями зависит от реализации.  
  
 B1241: для обеспечения корреляции сообщений 2PC [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализации должны поддерживать `wsa:ReferenceParameters`, как описано в спецификации WS\-Addressing.  
  
## Обмен сообщениями приложений  
 Для сообщений, передаваемых между приложениями, приложения могут использовать любую привязку, если она удовлетворяет следующим требованиям безопасности.  
  
-   R2001: заголовок сообщений, передаваемых между приложениями, должен содержать заголовок `t:IssuedTokens` наряду с `CoordinationContext`.  
  
-   R2002: необходимо обеспечение целостности и конфиденциальности `t:IssuedToken`.  
  
 Заголовок `CoordinationContext` содержит `wscoor:Identifier`.Хотя определение `xsd:AnyURI` допускает использование и абсолютных, и относительных универсальных кодов ресурсов \(URI\), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает только идентификаторы `wscoor:Identifiers`, являющиеся абсолютными URI.  
  
 B2003: если идентификатор `wscoor:Identifier` контекста `wscoor:CoordinationContext` является относительным URI, из транзакционных служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] будут возвращаться сбои.  
  
## Примеры сообщений  
  
### Сообщения запроса и ответа CreateCoordinationContext  
 Следующие сообщения соответствуют шаблону "запрос\-ответ".  
  
#### CreateCoordinationContext по WSCoor 1.0  
  
```  
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
  
#### CreateCoordinationContext по WSCoor 1.1  
  
```  
<s:Envelope>   
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
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
  
#### CreateCoordinationContextResponse по Trust версии до 1.3 и WSCoor 1.0  
  
```  
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
  
#### CreateCoordinationContextResponse по Trust 1.3 и WSCoor 1.1  
  
```  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->   
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>   
<t:IssuedTokens>   
<wst:RequestSecurityTokenResponse   
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"   
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-     wssecurity-utility-1.0.xsd"   
xmlns:wst=http://docs.oasis-open.org/ws-sx/ws-trust/200512  
xmlns:wsc=http://schemas.xmlsoap.org/ws/2005/02/sc  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>   
<wsc:SecurityContextToken>   
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>   
</wsc:SecurityContextToken>   
</wst:RequestedSecurityToken>   
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
<wst:RequestedAttachedReference>   
<wsse:SecurityTokenReference >   
<wsse:Reference  
  ValueType=http://schemas.xmlsoap.org/ws/2005/02/sc/sct  
  URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedAttachedReference>   
<wst:RequestedUnattachedReference>   
<wsse:SecurityTokenReference>   
<wsse:Reference  
 ValueType=http://schemas.xmlsoap.org/ws/2005/02/sc/sct  
 URI="http://fabrikam123.com/SCTi"/>  
</wsse:SecurityTokenReference>   
</wst:RequestedUnattachedReference>   
<wst:RequestedProofToken>   
<wst:BinarySecret  
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
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
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>   
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>   
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>   
</wscoor:CoordinationContext>   
</wscoor:CreateCoordinationContextResponse>   
</s:Body>   
</s:Envelope>  
  
```  
  
### Сообщения регистрации  
 Следующие сообщения являются сообщениями регистрации.  
  
#### Register по WSCoor 1.0  
  
```  
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
  
#### Register по WSCoor 1.1  
  
```  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>   
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
<wssu:Identifier> http://fabrikam123.com/SCTi  
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
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>   
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>   
</ds:Reference>   
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>   
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
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
  
#### RegisterResponse по WSCoor 1.0  
  
```  
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
  
#### RegisterResponse по WSCoor 1.1  
  
```  
<s:Envelope>  
<s:Header>   
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>   
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
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
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>   
</wscoor:RegisterResponse>   
</s:Body>   
</s:Envelope>  
  
```  
  
### Сообщения протокола двухфазной фиксации  
 Следующее сообщение относится к протоколу двухфазной фиксации \(2PC\).  
  
#### Commit по WSAT 1.0  
  
```  
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
  
#### Commit по WSAT 1.1  
  
```  
<s:Envelope>  
<s:Header>   
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
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
  
### Сообщения приложений  
 Следующие сообщения являются сообщениями приложений.  
  
#### Сообщение приложения — запрос  
  
```  
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