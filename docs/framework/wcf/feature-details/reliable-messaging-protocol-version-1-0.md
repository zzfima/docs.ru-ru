---
title: "Протокол надежного обмена сообщениями, версия 1.0 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Протокол надежного обмена сообщениями, версия 1.0
В этом разделе описаны особенности реализации в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] протокола WS\-Reliable Messaging \(версия 1.0, февраль 2005\), необходимого для взаимодействия с использованием транспорта HTTP.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] соблюдена спецификация WS\-Reliable Messaging с некоторыми ограничениями и пояснениями, описанными в этом разделе.Обратите внимание, что протокол WS\-ReliableMessaging версии 1.0 реализуется начиная с версии [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 Версия протокола WS\-Reliable Messaging от февраля 2005 г. реализована в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью класса <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Для удобства объяснения в этом разделе используются следующие роли:  
  
-   инициатор: клиент, инициирующий создание последовательности сообщений WS\-Reliable;  
  
-   респондент: служба, получающая запросы инициатора.  
  
 В этом документе используются префиксы и пространства имен, описанные в следующей таблице.  
  
|Префикс|Пространство имен|  
|-------------|-----------------------|  
|wsrm|http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/rm|  
|netrm|http:\/\/schemas.microsoft.com\/ws\/2006\/05\/rm|  
|s|http:\/\/www.w3.org\/2003\/05\/soap\-envelope|  
|wsa|http:\/\/schemas.xmlsoap.org\/ws\/2005\/08\/addressing|  
|wsse|http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wssecurity\-secext\-1.0.xsd|  
  
## Обмен сообщениями  
  
### Сообщения установления последовательности  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализованы сообщения `CreateSequence` и `CreateSequenceResponse`, позволяющие установить последовательность надежных сообщений.Действуют следующие ограничения.  
  
-   B1101: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создает необязательный элемент "Expires" в сообщении `CreateSequence` или, если сообщение `CreateSequence` содержит элемент `Offer`, необязательный элемент `Expires` в элементе `Offer`.  
  
-   B1102: при обращении к сообщению `CreateSequence` инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` отправляет и получает оба элемента `Expires`, если они существуют, но не использует их значения.  
  
 Протокол WS\-Reliable Messaging использует механизм `Offer` для формирования двух коррелированных встречных последовательностей, которые составляют сеанс.  
  
-   R1103: если сообщение `CreateSequence` содержит элемент `Offer`, респондент системы надежного обмена сообщениями должен либо принять последовательности и выдать ответ `CreateSequenceResponse`, который содержит элемент `wsrm:Accept`, образующий две коррелированных встречных последовательности, либо отклонить запрос `CreateSequence`.  
  
-   R1104: `SequenceAcknowledgement` и сообщения приложения, передаваемые во встречной последовательности, должны быть отправлены по адресу ссылки конечной последовательности `ReplyTo` в `CreateSequence`.  
  
-   R1105: адреса ссылок на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны совпадать на уровне октетов.  
  
     Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, чтобы совпадал фрагмент ссылки на конечные точки `AcksTo` и `ReplyTo`, обозначающий универсальный код ресурса \(URI\).  
  
-   R1106: ссылки на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.  
  
     В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предполагается, что \[параметры ссылок\] `AcksTo` и `ReplyTo` в сообщении `CreateSequence` совпадают и используют \[параметры ссылок\] из ссылки на конечную точку `ReplyTo` в подтверждениях и сообщениях встречной последовательности.  
  
-   R1107: при установке двух встречных последовательностей с помощью механизма `Offer` сообщение `SequenceAcknowledgement` и сообщения приложения во встречных последовательностях должны отправляться по ссылке на конечную точку `ReplyTo` в сообщении `CreateSequence`.  
  
-   R1108: при установке двух встречных последовательностей с помощью механизма "Offer" свойство `[address]` дочернего элемента ссылки на конечную точку `wsrm:AcksTo` элемента `wsrm:Accept` в сообщении `CreateSequenceResponse` должно с точностью до байта совпадать с универсальным кодом ресурса \(URI\) назначения сообщения `CreateSequence`.  
  
-   R1109: при установке двух встречных последовательностей с помощью механизма `Offer` сообщения, отправленные инициатором, и подтверждения на сообщения респондента должны отправляться по одной и той же ссылке на конечную точку.  
  
     В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] протокол WS\-Reliable Messaging используется для установки надежных сеансов между инициатором и респондентом.Реализация протокола WS\-Reliable Messaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает создание надежного сеанса для односторонней связи, обмена запросами и ответами и для полнодуплексного обмена сообщениями.Механизм `Offer` протокола WS\-Reliable Messaging в сообщениях `CreateSequence` и `CreateSequenceResponse` позволяет устанавливать две коррелированные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями.Поскольку платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] гарантирует безопасность таких сеансов, включая сквозную защиту для обеспечения целостности сеанса, она позволяет проверять, что сообщения, предназначенные одной и той же стороне, достигнут одной и той точки назначения.Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений.Таким образом, ограничения R1104, R1105 и R1108 относятся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Пример сообщения `CreateSequence`.  
  
```  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence  
    </a:Action>  
    <a:ReplyTo>  
      <a:Address>          
         http://Business456.com/clientA        
      </a:Address>  
    </a:ReplyTo>  
    <a:MessageID>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:MessageID>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
       <wsa:Address>  
         http://Business456.com/clientA  
       </wsa:Address>  
     </wsrm:AcksTo>  
     <wsrm:Offer>  
      <wsrm:Identifier>  
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496  
      </wsrm:Identifier>  
     </wsrm:Offer>  
   </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 Пример сообщения `CreateSequenceResponse`.  
  
```  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse  
    </a:Action>  
    <a:RelatesTo>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:RelatesTo>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
   <wsrm:CreateSequenceResponse>  
    <Identifier>  
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386  
    </Identifier>  
    <Accept>  
    <AcksTo>  
      <a:Address>  
        http://BusinessABC.com/serviceA  
      </a:Address>  
    </AcksTo>  
    </Accept>  
   </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### Последовательность  
 Ниже приведен список ограничений, относящихся к последовательностям.  
  
-   B1201:в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создаются и используются номера последовательностей, не превышающие максимального значения типа `xs:long` \(9223372036854775807\).  
  
-   B1202: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создается последнее сообщение с пустым телом и универсальным кодом ресурса \(URI\) действия http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/rm\/LastMessage.  
  
-   B1203: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сообщение получается и отправляется с заголовком последовательности, содержащим элемент `LastMessage`, при условии, что значение универсального кода ресурса \(URI\) действия не равно http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/rm\/LastMessage.  
  
 Пример заголовка последовательности.  
  
```  
<wsrm:Sequence>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
  <wsrm:MessageNumber>  
    10  
  </wsrm:MessageNumber>  
  <wsrm:LastMessage/>  
 </wsrm:Sequence>  
```  
  
### Заголовок AckRequested  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в качестве механизма поддержки активности используется заголовок `AckRequested`.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создается необязательный элемент `MessageNumber`.При получении сообщения с заголовком `AckRequested`, содержащим элемент `MessageNumber`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] игнорирует значение элемента `MessageNumber`, как показано в следующем примере.  
  
```  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### Заголовок SequenceAcknowledgement  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для передачи подтверждений последовательностей протокола WS\-Reliable Messaging используются сообщения приложений.  
  
-   R1401: при установке двух встречных последовательностей с помощью механизма `Offer` заголовок `SequenceAcknowledgement` может включаться в любое сообщение приложения, передаваемое определенному получателю.  
  
-   B1402: когда в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] необходимо создать подтверждение перед получением любых сообщений последовательности \(например, чтобы соответствовать требованиям сообщения `AckRequested`\), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает заголовок `SequenceAcknowledgement`, содержащий диапазон 0\-0, как показано в следующем примере.  
  
    ```  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются заголовки `SequenceAcknowledgement`, содержащие элемент `Nack`, но поддерживаются элементы `Nack`.  
  
### Ошибки протокола WS\-ReliableMessaging  
 Ниже приведен список ограничений, относящихся к реализации ошибок протокола WS\-Reliable Messaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B1501: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются ошибки `MessageNumberRollover`.  
  
-   B1502: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] конечная точка может создавать ошибки `CreateSequenceRefused`, описанные в спецификации.  
  
-   B1503: когда в конечной точке службы достигается максимальное число подключений и обработка новых подключений становится невозможной, среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает дополнительный вложенный код ошибки `CreateSequenceRefused`, `netrm:ConnectionLimitReached`, как показано в следующем примере.  
  
    ```  
    <s:Envelope>  
      <s:Header>  
        <wsa:Action>  
          http://schemas.xmlsoap.org/ws/2005/08/addressing/fault  
        </wsa:Action>  
      </s:Header>  
      <s:Body>  
        <s:Fault>  
          <s:Code>  
            <s:Value>  
              s:Receiver  
            </s:Value>  
            <s:Subcode>  
              <s:Value>  
                wsrm:CreateSequenceRefused  
              </s:Value>  
              <s:Subcode>  
                <s:Value>  
                  netrm:ConnectionLimitReached  
                </s:Value>  
              </s:Subcode>  
            </s:Subcode>  
          </s:Code>  
          <s:Reason>  
            <s:Text xml:lang="en">  
              [Reason]  
            </s:Text>  
          </s:Reason>  
        </s:Fault>  
      </s:Body>  
    </s:Envelope>  
    ```  
  
### Ошибки WS\-Addressing  
 Поскольку протокол WS\-Reliable Messaging использует протокол WS\-Addressing, реализация WS\-Reliable Messaging [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может создавать и передавать ошибки WS\-Addressing.В этом разделе описаны ошибки WS\-Addressing, которые среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]явным образом создает и передает на уровне WS\-Reliable Messaging.  
  
-   B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает ошибку "Требуется заголовок адресации сообщения", если выполняется одно из следующих условий:  
  
    -   в сообщении отсутствуют заголовки `Sequence` и `Action`;  
  
    -   в сообщении `CreateSequence` отсутствует заголовок `MessageId`;  
  
    -   в сообщении `CreateSequence` отсутствует заголовок `ReplyTo`.  
  
-   B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает ошибку "Действие не поддерживается" в ответ на сообщение об отсутствующем заголовке `Sequence` и наличии заголовка `Action`, не распознанного спецификацией WS\-Reliable Messaging.  
  
-   B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает ошибку "Конечная точка недоступна", указывающую на то, что конечная точка не обрабатывает последовательность на основании проверки заголовков адресов в сообщении `CreateSequence`.  
  
## Сочетаемость протокола  
  
### Сочетаемость с WS\-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает две версии протокола WS\-Addressing: WS\-Addressing 2004\/08 \[WS\-ADDR\] и рекомендации консорциума W3C по протоколу WS\-Addressing версии 1.0 \[WS\-ADDR\-CORE\] и \[WS\-ADDR\-SOAP\].  
  
 Поскольку в спецификации протокола WS\-Reliable Messaging указана только версия WS\-Addressing 2004\/08, он не накладывает ограничений на используемую версию WS\-Addressing.Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   R2101:с протоколом WS\-Reliable Messaging можно использовать как версию WS\-Addressing 2004\/08, так и версию WS\-Addressing 1.0.  
  
-   R2102:в рамках заданной последовательности WS\-Reliable Messaging или пары встречных последовательностей, коррелированных с помощью механизма `wsrm:Offer`, следует использовать только одну версию WS\-Addressing.  
  
### Сочетаемость с SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает использование с протоколом WS\-Reliable Messaging как версии SOAP 1.1, так и версии SOAP 1.2.  
  
### Сочетаемость с WS\-Security и WS\-SecureConversation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает защиту последовательностей WS\-Reliable Messaging с помощью безопасного транспорта \(HTTPS\) и совместимости с протоколами WS\-Security и WS\-Secure Conversation.Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   R2301:в дополнение к обеспечению целостности и конфиденциальности отдельных сообщений для защиты целостности последовательности WS\-Reliable Messaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требуется использовать протокол WS\-Secure.  
  
-   R2302:перед установкой последовательностей WS\-Reliable Messaging должен быть установлен сеанс WS\-Secure Conversation.  
  
-   R2303: если время существования последовательности WS\-Reliable Messaging превышает время существования сеанса WS\-Secure Conversation, необходимо с помощью привязки обновления WS\-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS\-Secure Conversation.  
  
-   B2304:последовательность WS\-Reliable Messaging или пара встречных последовательностей всегда ограничены одним сеансом WS\-SecureConversation.  
  
     Источник в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `wsse:SecurityTokenReference`, используя раздел расширения элемента заголовка в сообщении `CreateSequence`.  
  
-   R2305:при использовании с протоколом WS\-Secure Conversation необходимо, чтобы сообщение `CreateSequence` содержало элемент `wsse:SecurityTokenReference`.  
  
## Утверждение WS\-Reliable Messaging WS\-Policy  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] утверждение WS\-Reliable Messaging WS\-Policy `wsrm:RMAssertion` используется для описания возможностей конечных точек.Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] прикрепляет утверждение WS\-Policy `wsrm:RMAssertion` к элементам `wsdl:binding`.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает вложения для элементов `wsdl:binding` и `wsdl:port`.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает следующие дополнительные свойства утверждения WS\-Reliable Messaging и реализует контроль над ними через элемент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     Пример.  
  
    ```  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## Расширение WS\-Reliable Messaging для управления потоком  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует расширяемость WS\-Reliable Messaging, чтобы обеспечить более строгий контроль над потоком сообщений последовательности.  
  
 Чтобы включить управление потоком, необходимо присвоить свойству `FlowControlEnabled` типа `bool` элемента `ReliableSessionBindingElement` значение `true`.Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B4001: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `netrm:BufferRemaining`, используя возможности расширения элемента заголовка `SequenceAcknowledgement`.  
  
-   B4002: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требует наличия элемента `netrm:BufferRemaining` в заголовке `SequenceAcknowledgement`, как показано в следующем примере.  
  
    ```  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        http://fabrikam123.com/abc  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>  
        8  
      </netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
  
    ```  
  
-   B4003: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется элемент `netrm:BufferRemaining`, чтобы задать количество новых сообщений, которые точка назначения системы надежного обмена сообщениями может поместить в буфер.  
  
-   B4004:В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] служба надежного обмена сообщениями ограничивает количество передаваемых сообщений, когда приложение точки назначения системы надежного обмена сообщениями не может оперативно принять сообщения.Точка назначения системы надежного обмена сообщениями помещает сообщения в буфер, и значение элемента снижается до 0.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает целые значения элемента `netrm:BufferRemaining` в интервале от 0 до 4096 включительно и считывает целые значения в интервале от 0 до максимального значения типа `xs:int` \(`maxInclusive`, 214748364\) включительно.  
  
## Шаблоны обмена сообщениями  
 В этом разделе описана работа среды [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании протокола WS\-Reliable Messaging для различных шаблонов обмена сообщениями.Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:  
  
-   неадресуемый инициатор — инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP\-ответами;  
  
-   адресуемый инициатор — как инициатор, так и респондент могут принимать HTTP\-запросы, т. е. можно установить два встречных HTTP\-подключения.  
  
### Односторонний неадресуемый инициатор  
  
#### Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используются HTTP\-запросы для передачи всех сообщений от диспетчеров ресурсов в RMD и HTTP\-ответы для передачи всех сообщений от RMD к диспетчеру ресурсов.  
  
#### Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` без предложений.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` нет предложений перед созданием последовательности.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос `CreateSequence` сообщением `CreateSequenceResponse`.  
  
#### SequenceAcknowledgement  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает подтверждения при ответе на все сообщения, кроме сообщения `CreateSequence` и сообщений об ошибках.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создает отдельное подтверждение в HTTP\-ответе для сообщений последовательности и сообщений `AckRequested`.  
  
#### Сообщение TerminateSequence  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сообщение `TerminateSequence` рассматривается как односторонняя операция, т.е. HTTP\-ответы имеют пустое тело и код состояния HTTP 202.  
  
### Односторонний адресуемый инициатор  
  
#### Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями через один входящий и один исходящий канал HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP\-запросы.Все HTTP\-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` без предложений.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` нет предложений перед созданием последовательности.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequenceResponse` в HTTP\-запросе с помощью ссылки на конечную точку `ReplyTo`.  
  
### Дуплексный адресуемый инициатор  
  
#### Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон полностью асинхронного двустороннего обмена сообщениями с использованием двух последовательностей через один входящий и один исходящий канал HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP\-запросы.Все HTTP\-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением.Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет сообщение `CreateSequenceResponse` в HTTP\-запросе, направленном в конечную точку `CreateSequence``ReplyTo`.  
  
#### Время существования последовательности  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] две последовательности рассматриваются в качестве одного полнодуплексного сеанса.  
  
 После разрыва одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает, что удаленная точка доступа вызовет разрыв в обеих последовательностях.После чтения разрыва в одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вызывает разрывы в обеих последовательностях.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности.И наоборот, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.  
  
### Обмен сообщениями запрос\-ответ, неадресуемый инициатор  
  
#### Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон обмена сообщениями «запрос\-ответ» с использованием двух последовательностей через один входящий и один исходящий канал HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует HTTP\-запросы для передачи сообщений последовательности запросов и HTTP\-ответы для передачи сообщений последовательности ответов.  
  
#### Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением.Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос `CreateSequence` сообщением `CreateSequenceResponse`.  
  
#### Односторонний обмен сообщениями  
 Для реализации протокола одностороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP\-запросе и получает отдельное сообщение `SequenceAcknowledgement` в HTTP\-ответе.Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
#### Двусторонний обмен сообщениями  
 Для реализации протокола двустороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP\-запросе и получает сообщение последовательности ответов в HTTP\-ответе.Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
 Из\-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.  
  
#### Повторные попытки ответов  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для обеспечения корреляции между сообщениями протокола двустороннего обмена сообщениями используется корреляция между HTTP\-запросами и ответами.Поэтому инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не прекращает попытки отправки сообщения последовательности запросов в случае подтверждения этого сообщения, а дожидается HTTP\-ответа, содержащего подтверждение, пользовательское сообщение или ошибку.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] повторяет в HTTP\-запросе ответы на запрос, с которым коррелирует этот ответ.  
  
#### Обмен сообщениями LastMessage  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает последнее сообщение с пустым телом в HTTP\-запросе.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает ответ, но не учитывает само ответное сообщение.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос с последним пустым сообщением последовательности ответом с последним пустым сообщением последовательности.  
  
 Если респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] получает последнее сообщение, в котором значение универсального кода ресурса \(URI\) действия отлично от http:\/\/schemas.xmlsoap.org\/ws\/2005\/02\/rm\/LastMessage, среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает последним сообщением.В случае протокола двустороннего обмена сообщениями последнее сообщение содержит сообщение приложения, а в случае протокола одностороннего обмена сообщениями последнее сообщение будет пустым.  
  
 Для респондента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требуется подтверждение на ответ с последним пустым сообщением последовательности.  
  
#### Обмен сообщениями TerminateSequence  
 Когда на все запросы получен допустимый ответ, инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает сообщение последовательности запросов `TerminateSequence` в HTTP\-запросе.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает ответ, но не учитывает само ответное сообщение.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на сообщение `TerminateSequence` последовательности запроса сообщением `TerminateSequence` последовательности запроса.  
  
 В обычной последовательности отключения оба сообщения `TerminateSequence` содержат полный набор `SequenceAcknowledgement`.  
  
### Обмен сообщениями запрос\-ответ, адресуемый инициатор  
  
#### Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон обмена сообщениями «запрос\-ответ» с использованием двух последовательностей через один входящий и один исходящий канал HTTP.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP\-запросы.Все HTTP\-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением.Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет сообщение `CreateSequenceResponse` в HTTP\-запросе, направленном в конечную точку `CreateSequence``ReplyTo`.  
  
#### Корреляция запросов и ответов  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что все сообщения с запросами приложения содержат значение `MessageId` и ссылку на конечную точку `ReplyTo`.Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] применяет ссылку на конечную точку `ReplyTo` сообщения `CreateSequence` для каждого сообщения с запросом приложения.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует, чтобы все сообщения входящих запросов содержали значения `MessageId` и `ReplyTo`.Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что значения универсальных кодов ресурсов \(URI\) для ссылки на конечную точку в сообщении `CreateSequence` и во всех сообщениях запросов приложения идентичны.