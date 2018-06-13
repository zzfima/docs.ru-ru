---
title: Протокол надежного обмена сообщениями, версия 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: f45a0d5e50e9ab8a07a203d2c40ad36ef298a40d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497056"
---
# <a name="reliable-messaging-protocol-version-10"></a>Протокол надежного обмена сообщениями, версия 1.0
В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для протокола WS-Reliable Messaging protocol февраля 2005 г. (версия 1.0), необходимые для взаимодействия с использованием транспорта HTTP. WCF соответствует спецификации WS-Reliable Messaging с определенными ограничениями и пояснениями, описанными далее в этом разделе. Обратите внимание, что протокол WS-ReliableMessaging версии 1.0 реализуется начиная с версии [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 WS-ReliableMessaging February 2005 протокола реализован в WCF с <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Для удобства объяснения в этом разделе используются следующие роли:  
  
-   инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;  
  
-   респондент: служба, получающая запросы инициатора.  
  
 В этом документе используются префиксы и пространства имен, описанные в следующей таблице.  
  
|Префикс|Пространство имен|  
|------------|---------------|  
|wsrm|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a>Обмен сообщениями  
  
### <a name="sequence-establishment-messages"></a>Сообщения установления последовательности  
 Реализует WCF `CreateSequence` и `CreateSequenceResponse` сообщения, чтобы установить последовательность надежных сообщений. Действуют следующие ограничения.  
  
-   B1101: Инициатор WCF не создает необязательный элемент Expires в `CreateSequence` сообщений или в случаях при `CreateSequence` сообщение содержит `Offer` элемент, необязательный `Expires` элемент в `Offer` элемент.  
  
-   B1102: При доступе к `CreateSequence` сообщений WCF`Responder` отправляет и получает оба `Expires` элементов, если они существуют, но не использует их значения.  
  
 Протокол WS-Reliable Messaging использует механизм `Offer` для формирования двух коррелированных встречных последовательностей, которые составляют сеанс.  
  
-   R1103: если сообщение `CreateSequence` содержит элемент `Offer`, респондент системы надежного обмена сообщениями должен либо принять последовательности и выдать ответ `CreateSequenceResponse`, который содержит элемент `wsrm:Accept`, образующий две коррелированных встречных последовательности, либо отклонить запрос `CreateSequence`.  
  
-   R1104: `SequenceAcknowledgement` и сообщения приложения, передаваемые во встречной последовательности, должны быть отправлены по адресу ссылки конечной последовательности `ReplyTo` в `CreateSequence`.  
  
-   R1105: адреса ссылок на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны совпадать на уровне октетов.  
  
     Респондент WCF проверяет, что URI части `AcksTo` и `ReplyTo` ссылки на конечную точку идентичны перед созданием последовательности.  
  
-   R1106: ссылки на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.  
  
     WCF не применяет принудительно, но предполагается, что [параметры ссылок] `AcksTo` и `ReplyTo` на `CreateSequence` совпадают и используют [параметры ссылок] из `ReplyTo` ссылки на конечную точку в подтверждениях и сообщениях встречной последовательности.  
  
-   R1107: при установке двух встречных последовательностей с помощью механизма `Offer` сообщение `SequenceAcknowledgement` и сообщения приложения во встречных последовательностях должны отправляться по ссылке на конечную точку `ReplyTo` в сообщении `CreateSequence`.  
  
-   R1108: при установке двух встречных последовательностей с помощью механизма "Offer" свойство `[address]` дочернего элемента ссылки на конечную точку `wsrm:AcksTo` элемента `wsrm:Accept` в сообщении `CreateSequenceResponse` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.  
  
-   R1109: при установке двух встречных последовательностей с помощью механизма `Offer` сообщения, отправленные инициатором, и подтверждения на сообщения респондента должны отправляться по одной и той же ссылке на конечную точку.  
  
     WCF использует WS-Reliable Messaging для установки надежных сеансов между инициатором и респондентом. Реализация WS-Reliable Messaging WCF обеспечивает создание надежного сеанса для односторонней связи, запрос ответ и полной двустороннего обмена сообщениями. WS-Reliable Messaging `Offer` с помощью механизма `CreateSequence` / `CreateSequenceResponse` позволяет устанавливать две коррелированные встречные последовательности и обеспечивает протокол сеанса, которая подходит для всех конечных точках обмена сообщениями. Поскольку WCF гарантирует безопасность таких сеансов, включая защиты от начала до конца для обеспечения целостности сеанса, это целесообразно, чтобы убедиться, что сообщения, предназначенные для той же стороне поступают на то же назначение. Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений. Таким образом ограничения R1104, R1105 и R1108 применить к WCF.  
  
 Пример сообщения `CreateSequence`.  
  
```xml  
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
  
```xml  
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
  
### <a name="sequence"></a>Sequence  
 Ниже приведен список ограничений, относящихся к последовательностям.  
  
-   Создает B1201:WCF и обращается к порядковых номеров, не превышает `xs:long`максимальное значение включительно, 9223372036854775807.  
  
-   B1202:WCF всегда создает пустой последним сообщением с URI действия из http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
-   B1203: WCF получает и доставляет сообщение с заголовком последовательности, содержащий `LastMessage` элемент, при условии, что действие URI не http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
 Пример заголовка последовательности.  
  
```xml  
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
  
### <a name="ackrequested-header"></a>Заголовок AckRequested  
 WCF использует `AckRequested` заголовок как механизм поддержания активности. WCF не создает необязательный `MessageNumber` элемента. При получении сообщения с `AckRequested` заголовок, содержащий `MessageNumber` элемент, WCF игнорирует `MessageNumber` значение элемента, как показано в следующем примере.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>Заголовок SequenceAcknowledgement  
 WCF использует механизм обратной надстройка для подтверждений последовательностей в WS-Reliable Messaging.  
  
-   R1401: при установке двух встречных последовательностей с помощью механизма `Offer` заголовок `SequenceAcknowledgement` может включаться в любое сообщение приложения, передаваемое определенному получателю.  
  
-   B1402: Когда WCF необходимо создать подтверждение перед получением любых сообщений последовательности (например, для удовлетворения `AckRequested` сообщения), приводит к возникновению ошибки WCF `SequenceAcknowledgement` заголовок, содержащий диапазон 0-0, как показано в следующем примере.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: WCF не создает `SequenceAcknowledgement` заголовков, содержащих `Nack` элемент, но поддерживает `Nack` элементов.  
  
### <a name="ws-reliablemessaging-faults"></a>Ошибки протокола WS-ReliableMessaging  
 Ниже приведен список ограничений, относящихся к WCF реализации ошибок протокола WS-Reliable Messaging.  
  
-   B1501: WCF не создает `MessageNumberRollover` ошибок.  
  
-   Может создать конечную точку B1502:WCF `CreateSequenceRefused` ошибок, как описано в спецификации.  
  
-   B1503:When конечной точки службы достигает этого значения подключения и не может обработать новые подключения, WCF создает дополнительный `CreateSequenceRefused` код, ошибки `netrm:ConnectionLimitReached`, как показано в следующем примере.  
  
    ```xml  
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
  
### <a name="ws-addressing-faults"></a>Ошибки WS-Addressing  
 Так как WS-Reliable Messaging использует WS-Addressing, реализация WS-Reliable Messaging, WCF могут формироваться ошибки WS-Addressing. В этом разделе описаны ошибки WS-Addressing, которые WCF явно приводит к возникновению ошибки на уровне WS-Reliable Messaging:  
  
-   B1601:WCF приводит к возникновению ошибки требуется адресация заголовок сообщения при выполнении одного из следующих:  
  
    -   в сообщении отсутствуют заголовки `Sequence` и `Action`;  
  
    -   в сообщении `CreateSequence` отсутствует заголовок `MessageId`.  
  
    -   в сообщении `CreateSequence` отсутствует заголовок `ReplyTo`.  
  
-   B1602:WCF приводит к возникновению ошибки действие не поддерживается в ответ на сообщение, которое отсутствует `Sequence` заголовок и имеет `Action` заголовок, который не распознается в спецификации WS-Reliable Messaging.  
  
-   B1603:WCF формирует ошибку, конечная точка недоступна для указания, что конечной точки не обрабатывает последовательность на основании проверки `CreateSequence` заголовков адресов в сообщении.  
  
## <a name="protocol-composition"></a>Сочетаемость протокола  
  
### <a name="composition-with-ws-addressing"></a>Сочетаемость с WS-Addressing  
 WCF поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации W3C WS-Addressing 1.0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].  
  
 Поскольку в спецификации протокола WS-Reliable Messaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing. Ниже приведен список ограничений, относящихся к WCF:  
  
-   R2101: как можно использовать с WS-Reliable Messaging WS-Addressing 2004/08 и WS-Addressing 1.0.  
  
-   Необходимо использовать одну версию WS-Addressing R2102:A во всей заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью `wsrm:Offer` механизм.  
  
### <a name="composition-with-soap"></a>Сочетаемость с SOAP  
 WCF поддерживает использование SOAP 1.1 и SOAP 1.2 с WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Сочетаемость с WS-Security и WS-SecureConversation  
 WCF обеспечивает защиту последовательностей WS-Reliable Messaging с помощью безопасного транспорта (HTTPS), сочетаемость с WS-Security и сочетаемость с WS-Secure Conversation. Ниже приведен список ограничений, относящихся к WCF:  
  
-   R2301: для защиты целостности последовательности WS-Reliable Messaging в дополнение к целостности и конфиденциальности отдельных сообщений, WCF требуется, что необходимо использовать WS-Secure Conversation.  
  
-   R2302:AWS-Secure Conversation должен быть установлен до установки последовательностях WS-Reliable Messaging.  
  
-   R2303: если время существования последовательности WS-Reliable Messaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.  
  
-   B2304:ws-последовательности системы надежного обмена сообщениями или пару коррелированные встречные последовательности всегда привязан к одного сеанса WS-SecureConversation.  
  
     WCF-источник создает `wsse:SecurityTokenReference` элемент в раздел расширения элемента `CreateSequence` сообщения.  
  
-   Сочетание с WS-Secure Conversation R2305:When `CreateSequence` сообщение должно содержать `wsse:SecurityTokenReference` элемента.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Утверждение WS-Reliable Messaging WS-Policy  
 WCF использует утверждение WS-Reliable Messaging WS-Policy `wsrm:RMAssertion` для описания возможностей конечных точек. Ниже приведен список ограничений, относящихся к WCF:  
  
-   B3001: Присоединяет WCF `wsrm:RMAssertion` утверждение WS-Policy для `wsdl:binding` элементов. WCF поддерживает вложения в `wsdl:binding` и `wsdl:port` элементы.  
  
-   B3002: WCF поддерживает следующие дополнительные свойства утверждения WS-Reliable Messaging и реализует контроль над ними в WCF`ReliableMessagingBindingElement`:  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     Пример.  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a>Расширение WS-Reliable Messaging для управления потоком  
 WCF использует расширяемость WS-Reliable Messaging для обеспечения более строгий контроль над потоком последовательности сообщений.  
  
 Включить управление потоком, задав `ReliableSessionBindingElement` `FlowControlEnabled``bool` свойства `true`. Ниже приведен список ограничений, относящихся к WCF:  
  
-   B4001: Если включена надежного обмена сообщениями потока управления, WCF приводит к возникновению ошибки `netrm:BufferRemaining` элемент расширения элемента `SequenceAcknowledgement` заголовок.  
  
-   B4002: Если включена надежного обмена сообщениями потока управления, WCF не требует `netrm:BufferRemaining` элемента должны присутствовать в `SequenceAcknowledgement` заголовок, как показано в следующем примере.  
  
    ```xml  
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
  
-   B4003: WCF использует `netrm:BufferRemaining` буфера для указания того, сколько новых сообщений, назначения надежного обмена сообщениями.  
  
-   B4004: служба надежного обмена сообщениями WCF регулирует количество сообщений, передаваемых при приложения назначения надежного обмена сообщениями не может быстро получать сообщения. Точка назначения системы надежного обмена сообщениями помещает сообщения в буфер, и значение элемента снижается до 0.  
  
-   B4005: WCF формирует `netrm:BufferRemaining` integer значения от 0 до 4096 включительно и считывает целые значения в диапазоне от 0 и `xs:int` `maxInclusive` значение 214748364 включительно.  
  
## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями  
 Этот раздел описывает поведение WCF при использовании WS-Reliable Messaging для различных шаблонов обмена сообщениями. Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:  
  
-   неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;  
  
-   адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.  
  
### <a name="one-way-non-addressable-initiator"></a>Односторонний неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений от RMD и HTTP-ответа для передачи всех сообщений от RMD RMS.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 WCF-инициатора создает `CreateSequence` сообщение без предложений. Респондент WCF обеспечивает `CreateSequence` нет предложений перед созданием последовательности. Респондент WCF ответит на `CreateSequence` запрос с `CreateSequenceResponse` сообщения.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Инициатор WCF обрабатывает подтверждения при ответе на все сообщения, за исключением `CreateSequence` сообщений и сообщений об ошибках. Респондент WCF всегда создает отдельное подтверждение в ответ на оба последовательности и `AckRequested` сообщений.  
  
#### <a name="terminatesequence-message"></a>Сообщение TerminateSequence  
 Рассматривает WCF `TerminateSequence` как Односторонняя операция, т.е. HTTP-ответа имеют пустое тело и код состояния HTTP 202.  
  
### <a name="one-way-addressable-initiator"></a>Односторонний адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и исходящий канал Http. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 WCF-инициатора создает `CreateSequence` сообщение без предложений. Респондент WCF гарантирует, что `CreateSequence` нет предложений перед созданием последовательности. Респондент WCF передает `CreateSequenceResponse` решены сообщения HTTP-запроса с `ReplyTo` ссылки на конечную точку.  
  
### <a name="duplex-addressable-initiator"></a>Дуплексный адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет полностью асинхронного двустороннего обмена сообщениями с использованием двух последовательностей через входящий и исходящий канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 WCF-инициатора создает `CreateSequence` сообщение с предложением. Респондент WCF гарантирует, что `CreateSequence` есть предложение перед созданием последовательности. WCF отправляет `CreateSequenceResponse` в HTTP-запросе, направленном `CreateSequence` `ReplyTo` ссылки на конечную точку.  
  
#### <a name="sequence-lifetime"></a>Время существования последовательности  
 WCF две последовательности рассматриваются в качестве одного полнодуплексного сеанса.  
  
 При создании ошибки разрыва одной последовательности, WCF предполагает, что Удаленная конечная точка разрыв в обеих последовательностях. После чтения разрыва одной последовательности, WCF ошибках обеих последовательностях.  
  
 WCF можно закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности. И наоборот WCF может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.  
  
### <a name="request-reply-non-addressable-initiator"></a>Обмен сообщениями запрос-ответ, неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет одностороннее и шаблон обмена сообщениями запрос ответ, с использованием двух последовательностей через один канал HTTP. WCF использует HTTP-запросы для передачи сообщений последовательности запросов и использует HTTP-ответы для передачи сообщений последовательности ответа.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 WCF-инициатора создает `CreateSequence` сообщение с предложением. Респондент WCF гарантирует, что `CreateSequence` есть предложение перед созданием последовательности. Респондент WCF ответит на `CreateSequence` запрос с `CreateSequenceResponse` сообщения.  
  
#### <a name="one-way-message"></a>Односторонний обмен сообщениями  
 Для успешного завершения протокола одностороннего обмена сообщениями WCF инициатора передает сообщение последовательности запросов в HTTP-запросе и получает отдельное `SequenceAcknowledgement` сообщение HTTP-ответе. Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.  
  
 Респондент WCF может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
#### <a name="two-way-messages"></a>Двусторонний обмен сообщениями  
 Для реализации протокола двустороннего сообщений exchange, инициатор WCF передает сообщение последовательности запросов в HTTP-запросе и получает сообщение последовательности ответов в HTTP-ответе. Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.  
  
 Респондент WCF может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
 Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.  
  
#### <a name="retrying-replies"></a>Повторные попытки ответов  
 WCF использует корреляцию запросов и ответов HTTP для корреляции протокола двустороннего сообщений exchange. По этой причине инициатора WCF не прекращает попытки сообщение последовательности запросов подтверждения сообщение последовательности запросов, но вместо этого в том случае, когда ответа HTTP, содержащего подтверждение, пользовательское сообщение или ошибок. Респондент WCF повторяет ответы HTTP-запросе запроса, с которой связан этот ответ.  
  
#### <a name="lastmessage-exchange"></a>Обмен сообщениями LastMessage  
 WCF-инициатора создает и передает пустым телом последнее сообщение HTTP-запросе. WCF ожидает ответ, но не учитывает само ответное сообщение. Респондент WCF отвечает последовательности запросов пустым последним сообщением с последовательности ответа пустым последним сообщением.  
  
 Если респондент WCF получает последнее сообщение, в котором действие URI не http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, WCF отвечает последним сообщением. В случае протокола двустороннего обмена сообщениями последнее сообщение содержит сообщение приложения, а в случае протокола одностороннего обмена сообщениями последнее сообщение будет пустым.  
  
 Респондент WCF не требует подтверждения для последовательности ответа пустым последним сообщением.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 Если все запросы получен допустимый ответ, инициатор WCF создает и передает последовательности запросов `TerminateSequence` сообщение HTTP-запросе. WCF ожидает ответ, но не учитывает само ответное сообщение. Респондент WCF ответит на последовательности запросов `TerminateSequence` сообщения последовательности ответа `TerminateSequence` сообщения.  
  
 В обычной последовательности отключения оба сообщения `TerminateSequence` содержат полный набор `SequenceAcknowledgement`.  
  
### <a name="requestreply-addressable-initiator"></a>Обмен сообщениями запрос-ответ, адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон обмена сообщениями запрос ответ с использованием двух последовательностей через входящий и исходящий канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 WCF-инициатора создает `CreateSequence` сообщение с предложением. Респондент WCF гарантирует, что `CreateSequence` есть предложение перед созданием последовательности. WCF отправляет `CreateSequenceResponse` в HTTP-запросе, направленном `CreateSequence` `ReplyTo` ссылки на конечную точку.  
  
#### <a name="requestreply-correlation"></a>Корреляция запросов и ответов  
 Инициатор WCF обеспечивает все сообщения запроса приложения содержат `MessageId` и `ReplyTo` ссылки на конечную точку. Применяет инициатора WCF `CreateSequence` сообщения `ReplyTo` ссылки на конечную точку для каждого сообщения с запросом приложения. Респондент WCF требуется сообщения, входящих запросов содержали `MessageId` и `ReplyTo`. Респондент WCF гарантирует, что URI ссылки на конечную точку как `CreateSequence` и всех сообщений запросов приложения идентичны.
