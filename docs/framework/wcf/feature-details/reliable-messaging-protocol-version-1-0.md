---
title: Протокол надежного обмена сообщениями, версия 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: 857bbbf9ffa1311c38cfc007e0cdc6bde06d6284
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617568"
---
# <a name="reliable-messaging-protocol-version-10"></a>Протокол надежного обмена сообщениями, версия 1.0
В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для протокола WS-Reliable Messaging protocol февраля 2005 г. (версия 1.0), необходимые для взаимодействия с использованием транспорта HTTP. WCF соблюдена спецификация WS-Reliable Messaging с определенными ограничениями и пояснениями, описанными далее в этом разделе. Обратите внимание, что протокол WS-ReliableMessaging версии 1.0 реализуется начиная с версии [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 WS-Reliable Messaging от февраля 2005 протокола реализован в WCF, <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Для удобства объяснения в этом разделе используются следующие роли:  
  
- инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;  
  
- респондент: служба, получающая запросы инициатора.  
  
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
 В WCF реализована `CreateSequence` и `CreateSequenceResponse` сообщения, чтобы установить последовательность надежных сообщений. Действуют следующие ограничения.  
  
- B1101: Инициатор WCF не создает необязательный элемент Expires в `CreateSequence` сообщения или в случаях при `CreateSequence` сообщение содержит `Offer` элемент, необязательный `Expires` элемент в `Offer` элемент.  
  
- B1102: При доступе к `CreateSequence` сообщений WCF`Responder` отправляет и получает оба `Expires` элементов, если они существуют, но не использует их значения.  
  
 Протокол WS-Reliable Messaging использует механизм `Offer` для формирования двух коррелированных встречных последовательностей, которые составляют сеанс.  
  
- R1103: Если `CreateSequence` содержит `Offer` элемент, респондент должен либо принять последовательности и ответ с `CreateSequenceResponse` , содержащий `wsrm:Accept` элемент, образующий две коррелированных встречных последовательности, либо отклонить `CreateSequence`запроса.  
  
- R1104: `SequenceAcknowledgement` и сообщения приложения, передаваемые во встречной последовательности, должны быть отправлены по адресу ссылки конечной последовательности `ReplyTo` в `CreateSequence`.  
  
- R1105: адреса ссылок на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны совпадать на уровне октетов.  
  
     Респондент WCF проверяет, что часть URI `AcksTo` и `ReplyTo` ссылки на конечную точку идентичны перед созданием последовательности.  
  
- R1106: ссылки на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.  
  
     WCF не применяет принудительно, но предполагается, что [параметры ссылок] из `AcksTo` и `ReplyTo` на `CreateSequence` совпадают и используют [параметры ссылок] из `ReplyTo` ссылки на конечную точку в подтверждениях и сообщениях встречной последовательности.  
  
- R1107: При установлении двух встречных последовательностей с помощью `Offer` механизм, `SequenceAcknowledgement` и сообщения приложения во встречных последовательностях должны отправляться `ReplyTo` ссылки на конечную точку из `CreateSequence`.  
  
- R1108: При установлении двух встречных последовательностей с помощью механизма предложения, `[address]` свойство `wsrm:AcksTo` дочернего элемента ссылки на конечную точку `wsrm:Accept` элемент `CreateSequenceResponse` должно соответствовать побайтно URI назначения `CreateSequence`.  
  
- R1109: При установлении двух встречных последовательностей с помощью `Offer` механизм, сообщения, отправленные инициатором и подтверждения на сообщения респондента должны отправляться в одну и ту же ссылку конечной точки.  
  
     WCF использует WS-Reliable Messaging для установки надежных сеансов между инициатором и респондентом. Реализация WS-Reliable Messaging WCF обеспечивает создание надежного сеанса для односторонней связи, запрос ответ и полный двустороннего обмена сообщениями. WS-Reliable Messaging `Offer` механизма `CreateSequence` / `CreateSequenceResponse` позволяет устанавливать две коррелированные встречные последовательности и обеспечивает протокол сеанса, который подходит для всех конечных точках обмена сообщениями. Так как WCF гарантирует безопасность таких сеансов, включая защиту end-to-end для обеспечения целостности сеанса, целесообразно убедиться, что сообщения, предназначенные для той же стороне поступают на этом же месте назначения. Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений. Таким образом ограничения R1104, R1105 и R1108 применяются к WCF.  
  
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
  
- Создает B1201:WCF и обращается к порядковые номера, не превышающие `xs:long`его максимального значения 9223372036854775807.  
  
- B1202:WCF всегда создает пустым последнее сообщение с действием URI из `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
- B1203: WCF получает и доставляет ему сообщение с заголовком последовательности, содержащий `LastMessage` элемент, пока не является URI действия `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
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
 WCF использует `AckRequested` заголовок как механизм поддержания активности. WCF не создает необязательный `MessageNumber` элемент. При получении сообщения с `AckRequested` заголовок, содержащий `MessageNumber` элемент, WCF игнорирует `MessageNumber` значение элемента, как показано в следующем примере.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>Заголовок SequenceAcknowledgement  
 WCF использует подтверждений для подтверждений последовательностей в WS-Reliable Messaging.  
  
- R1401: При установлении двух встречных последовательностей с помощью `Offer` механизм, `SequenceAcknowledgement` заголовка может быть включено в любое сообщение приложения предполагаемому получателю.  
  
- B1402: Когда WCF необходимо создать подтверждение перед получением любых сообщений последовательности (например, для удовлетворения `AckRequested` сообщение), WCF создает `SequenceAcknowledgement` заголовок, содержащий диапазон 0-0, как показано в следующем примере.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
- B1403: WCF не создает `SequenceAcknowledgement` заголовков, содержащих `Nack` элемент, но поддерживает `Nack` элементов.  
  
### <a name="ws-reliablemessaging-faults"></a>Ошибки протокола WS-ReliableMessaging  
 Ниже приведен список ограничений, относящихся к реализации ошибок протокола WS-Reliable Messaging WCF:  
  
- B1501: WCF не создает `MessageNumberRollover` ошибок.  
  
- Конечная точка B1502:WCF может создавать `CreateSequenceRefused` ошибок, как описано в спецификации.  
  
- B1503:When конечную точку службы достигает достигается максимальное число подключений и не может обработать новые подключения, WCF создает дополнительный `CreateSequenceRefused` код ошибки, `netrm:ConnectionLimitReached`, как показано в следующем примере.  
  
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
 Так как WS-Reliable Messaging использует протокол WS-Addressing, реализация WS-Reliable Messaging WCF может генерировать ошибки WS-Addressing. В этом разделе описаны ошибки WS-Addressing, которые явно создает WCF на уровне WS-Reliable Messaging:  
  
- B1601:WCF создает ошибку, требуется заголовок адресации сообщения, если выполняется одно из следующих:  
  
    - в сообщении отсутствуют заголовки `Sequence` и `Action`;  
  
    - в сообщении `CreateSequence` отсутствует заголовок `MessageId`.  
  
    - в сообщении `CreateSequence` отсутствует заголовок `ReplyTo`.  
  
- B1602:WCF создает ошибку, действие не поддерживается, ответ на сообщение, которое отсутствует `Sequence` заголовка и имеет `Action` заголовок, который не является распознанным в спецификации WS-Reliable Messaging.  
  
- B1603:WCF создает ошибку, конечная точка недоступна, чтобы указать, что конечная точка не обрабатывает последовательность на основании проверки `CreateSequence` заголовков адресов в сообщении.  
  
## <a name="protocol-composition"></a>Сочетаемость протокола  
  
### <a name="composition-with-ws-addressing"></a>Сочетаемость с WS-Addressing  
 WCF поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и W3C WS-Addressing 1.0 рекомендации [WS-ADDR-CORE] и [WS-ADDR-SOAP].  
  
 Поскольку в спецификации протокола WS-Reliable Messaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing. Ниже приведен список ограничений, относящихся к WCF:  
  
- R2101: как можно использовать с WS-Reliable Messaging WS-Addressing 2004/08, так и WS-Addressing 1.0.  
  
- R2102:A одну версию WS-Addressing должны использоваться заданной последовательности WS-Reliable Messaging или пары встречных последовательностей, коррелированных с помощью `wsrm:Offer` механизм.  
  
### <a name="composition-with-soap"></a>Сочетаемость с SOAP  
 WCF поддерживает использование протокола SOAP 1.1 и SOAP 1.2 с WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Сочетаемость с WS-Security и WS-SecureConversation  
 WCF обеспечивает защиту последовательностей WS-Reliable Messaging с помощью безопасного транспорта (HTTPS), сочетаемость с WS-Security и WS-Secure Conversation. Ниже приведен список ограничений, относящихся к WCF:  
  
- R2301: для защиты целостности последовательности WS-Reliable Messaging в дополнение к целостности и конфиденциальности отдельных сообщений, WCF требует, что необходимо использовать WS-Secure Conversation.  
  
- R2302:AWS-Secure Conversation сеанса должно быть установлено перед установкой последовательностей WS-Reliable Messaging.  
  
- R2303: Если время существования последовательности WS-Reliable Messaging WS-Secure Conversation превышает время существования сеанса `SecurityContextToken` установить с помощью WS-Secure Conversation должен обновляться с помощью привязки обновления WS-Secure Conversation.  
  
- B2304:ws-последовательности Reliable Messaging или пары встречных последовательностей всегда ограничены одним сеансом WS-SecureConversation.  
  
     Источник WCF создает `wsse:SecurityTokenReference` элемент в раздел расширения элемента `CreateSequence` сообщения.  
  
- С WS-Secure Conversation R2305:When `CreateSequence` сообщение должно содержать `wsse:SecurityTokenReference` элемент.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Утверждение WS-Reliable Messaging WS-Policy  
 WCF использует утверждение WS-Reliable Messaging WS-Policy `wsrm:RMAssertion` для описания возможностей конечных точек. Ниже приведен список ограничений, относящихся к WCF:  
  
- B3001: WCF присоединяет `wsrm:RMAssertion` утверждение WS-Policy для `wsdl:binding` элементов. WCF поддерживает вложения в `wsdl:binding` и `wsdl:port` элементы.  
  
- B3002: WCF поддерживает следующие дополнительные свойства утверждения WS-Reliable Messaging и реализует контроль над ними на WCF`ReliableMessagingBindingElement`:  
  
    - `wsrm:InactivityTimeout`  
  
    - `wsrm:AcknowledgementInterval`  
  
     Пример.  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a>Расширение WS-Reliable Messaging для управления потоком  
 WCF использует расширяемость WS-Reliable Messaging для предоставления необязательно более строгий контроль над потоком последовательности сообщений.  
  
 Управление потоком можно включить, задав <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> свойства `true`. Ниже приведен список ограничений, относящихся к WCF:  
  
- B4001: При включении надежного обмена сообщениями потока управления, WCF создает `netrm:BufferRemaining` элемент расширения элемента `SequenceAcknowledgement` заголовка.  
  
- B4002: При включении надежного обмена сообщениями потока управления, WCF не требует `netrm:BufferRemaining` элемента должны присутствовать в `SequenceAcknowledgement` заголовка, как показано в следующем примере.  
  
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
  
- B4003: WCF использует `netrm:BufferRemaining` чтобы указать число новых сообщений, надежный обмен сообщениями целевой размер буфера.  
  
- B4004: служба надежного обмена сообщениями WCF регулирует количество передаваемых сообщений, когда приложения назначения системы надежного обмена сообщениями не может оперативно принять сообщения. Точка назначения системы надежного обмена сообщениями помещает сообщения в буфер, и значение элемента снижается до 0.  
  
- B4005: WCF создает `netrm:BufferRemaining` целое число значений в диапазоне от 0 до 4096 включительно и считывает целые значения между 0 и `xs:int`в `maxInclusive` значение 214748364 включительно.  
  
## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями  
 В этом разделе описывает поведение WCF, когда WS-Reliable Messaging используется для различных шаблонов обмена сообщениями. Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:  
  
- Неадресуемый инициатор Инициатор расположен за брандмауэром; Отвечающее устройство можно отправлять инициатору сообщения только с HTTP-ответами.  
  
- Адресуемый инициатор Инициатор и отвечающее устройство можно отправлять HTTP-запросов; Другими словами можно установить два встречных HTTP-подключения.  
  
### <a name="one-way-non-addressable-initiator"></a>Односторонний неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений из RMS в RMD и HTTP-ответа для передачи всех сообщений от RMD имя корневого сервера управления.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF создает `CreateSequence` сообщение без предложений. Респондент WCF `CreateSequence` нет предложений перед созданием последовательности. Респондент WCF отвечает `CreateSequence` запрос с `CreateSequenceResponse` сообщения.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Инициатор WCF обрабатывает подтверждения при ответе на все сообщения, за исключением `CreateSequence` сообщений и сообщений об ошибках. Респондент WCF всегда создает отдельное подтверждение в ответ на оба последовательности и `AckRequested` сообщений.  
  
#### <a name="terminatesequence-message"></a>Сообщение TerminateSequence  
 Обрабатывает WCF `TerminateSequence` как Односторонняя операция, то есть HTTP-ответа имеет пустым телом и кодом состояния HTTP 202.  
  
### <a name="one-way-addressable-initiator"></a>Односторонний адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и исходящий канал Http. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF создает `CreateSequence` сообщение без предложений. Респондент WCF гарантирует, что `CreateSequence` нет предложений перед созданием последовательности. Респондент WCF передает `CreateSequenceResponse` устранены сообщение HTTP-запрос с помощью `ReplyTo` ссылки на конечную точку.  
  
### <a name="duplex-addressable-initiator"></a>Дуплексный адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF поддерживает шаблон полностью асинхронного двустороннего обмена с использованием двух последовательностей через один входящий и исходящий канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF создает `CreateSequence` сообщение с предложением. Респондент WCF гарантирует, что `CreateSequence` есть предложение перед созданием последовательности. WCF отправляет `CreateSequenceResponse` HTTP-запросу адресованный `CreateSequence`в `ReplyTo` ссылки на конечную точку.  
  
#### <a name="sequence-lifetime"></a>Время существования последовательности  
 WCF две последовательности рассматриваются в качестве одного полнодуплексного сеанса.  
  
 После создания разрыва одной последовательности, WCF предполагает, что Удаленная конечная точка сбой обоих последовательностей. После чтения разрыва в одной последовательности, WCF создает ошибки обоих последовательностей.  
  
 WCF можно закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности. И наоборот WCF может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.  
  
### <a name="request-reply-non-addressable-initiator"></a>Обмен сообщениями запрос-ответ, неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет одностороннее и шаблон обмена сообщениями типа запрос ответ, с использованием двух последовательностей через один канал HTTP. WCF использует HTTP-запросы для передачи сообщений последовательности запросов и использует HTTP-ответы для передачи сообщений последовательности ответов.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF создает `CreateSequence` сообщение с предложением. Респондент WCF гарантирует, что `CreateSequence` есть предложение перед созданием последовательности. Респондент WCF отвечает `CreateSequence` запрос с `CreateSequenceResponse` сообщения.  
  
#### <a name="one-way-message"></a>Односторонний обмен сообщениями  
 Для реализации протокола одностороннего обмена успешно, инициатор WCF передает сообщение последовательности запросов в HTTP-запрос и получает отдельное `SequenceAcknowledgement` сообщение на HTTP-ответа. Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.  
  
 Респондент WCF может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
#### <a name="two-way-messages"></a>Двусторонний обмен сообщениями  
 Для реализации протокола двустороннего сообщений exchange, инициатор WCF передает сообщение последовательности запросов в HTTP-запрос и получает сообщение последовательности ответов на HTTP-ответа. Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.  
  
 Респондент WCF может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
 Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.  
  
#### <a name="retrying-replies"></a>Повторные попытки ответов  
 WCF использует корреляцию запросов и ответов HTTP для корреляции протокола двустороннего обмена. По этой причине инициатора WCF прекращает попытки отправки сообщение последовательности запросов, когда подтверждается сообщение последовательности запросов, но вместо этого в том случае, когда ответа HTTP, содержащего подтверждение, пользовательское сообщение или сбоя. Респондент WCF повторяет ответы в запрос HTTP-запроса, к которому связан этот ответ.  
  
#### <a name="lastmessage-exchange"></a>Обмен сообщениями LastMessage  
 Инициатор WCF создает и передает последнее сообщение пустым телом в HTTP-запроса. WCF требует ответ, но игнорирует само ответное сообщение. Респондент WCF отвечает последовательности запросов пустым последнее сообщение с пустым телом последнее сообщение последовательности ответов.  
  
 Если респондент WCF получает последнее сообщение, в котором действие URI не `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF отвечает последним сообщением. В случае протокола двустороннего обмена сообщениями последнее сообщение содержит сообщение приложения, а в случае протокола одностороннего обмена сообщениями последнее сообщение будет пустым.  
  
 Респондент WCF не требует подтверждения для последовательности ответов пустой последним сообщением.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 Когда все запросы получен допустимый ответ, инициатор WCF создает и передает последовательности запросов `TerminateSequence` сообщение в HTTP-запроса. WCF требует ответ, но игнорирует само ответное сообщение. Респондент WCF отвечает последовательности запросов `TerminateSequence` сообщение последовательности ответов `TerminateSequence` сообщения.  
  
 В обычной последовательности отключения оба сообщения `TerminateSequence` содержат полный набор `SequenceAcknowledgement`.  
  
### <a name="requestreply-addressable-initiator"></a>Обмен сообщениями запрос-ответ, адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон обмена сообщениями типа запрос ответ с использованием двух последовательностей через один входящий и исходящий канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF создает `CreateSequence` сообщение с предложением. Респондент WCF гарантирует, что `CreateSequence` есть предложение перед созданием последовательности. WCF отправляет `CreateSequenceResponse` HTTP-запросу адресованный `CreateSequence`в `ReplyTo` ссылки на конечную точку.  
  
#### <a name="requestreply-correlation"></a>Корреляция запросов и ответов  
 Инициатор WCF обеспечивает все сообщения запроса приложения содержат `MessageId` и `ReplyTo` ссылки на конечную точку. Инициатор WCF применяет `CreateSequence` сообщения `ReplyTo` ссылки на конечную точку для каждого сообщения с запросом приложения. Респондент WCF требует все сообщения этой входящих запросов содержат `MessageId` и `ReplyTo`. Респондент WCF гарантирует, что URI ссылки на конечную точку как `CreateSequence` и всех сообщений запросов приложения идентичны.
