---
title: "Протокол надежного обмена сообщениями, версия 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d204600682ec8acbc229240c4e1bc859d8ea4d21
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-messaging-protocol-version-10"></a>Протокол надежного обмена сообщениями, версия 1.0
В этом разделе описаны особенности реализации в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] протокола обмена сообщениями WS-Reliable (версия 1.0 от февраля 2005 года), необходимого для взаимодействия с использованием транспорта HTTP. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] соблюдена спецификация обмена сообщениями WS-Reliable с определенными ограничениями и пояснениями, описанными далее в этом разделе. Обратите внимание, что протокол WS-ReliableMessaging версии 1.0 реализуется начиная с версии [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
 Версия протокола WS-Reliable Messaging от февраля 2005 г. реализована в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью класса <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
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
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализованы сообщения `CreateSequence` и `CreateSequenceResponse`, позволяющие установить последовательность надежных сообщений. Действуют следующие ограничения.  
  
-   B1101: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создает необязательный элемент "Expires" в сообщении `CreateSequence` или, если сообщение `CreateSequence` содержит элемент `Offer`, необязательный элемент `Expires` в элементе `Offer`.  
  
-   B1102: при обращении к сообщению `CreateSequence` инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` отправляет и получает оба элемента `Expires`, если они существуют, но не использует их значения.  
  
 Протокол WS-Reliable Messaging использует механизм `Offer` для формирования двух коррелированных встречных последовательностей, которые составляют сеанс.  
  
-   R1103: если сообщение `CreateSequence` содержит элемент `Offer`, респондент системы надежного обмена сообщениями должен либо принять последовательности и выдать ответ `CreateSequenceResponse`, который содержит элемент `wsrm:Accept`, образующий две коррелированных встречных последовательности, либо отклонить запрос `CreateSequence`.  
  
-   R1104: `SequenceAcknowledgement` и сообщения приложения, передаваемые во встречной последовательности, должны быть отправлены по адресу ссылки конечной последовательности `ReplyTo` в `CreateSequence`.  
  
-   R1105: адреса ссылок на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны совпадать на уровне октетов.  
  
     Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, чтобы совпадал фрагмент ссылки на конечные точки `AcksTo` и `ReplyTo`, обозначающий универсальный код ресурса (URI).  
  
-   R1106: ссылки на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.  
  
     В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предполагается, что [параметры ссылок] `AcksTo` и `ReplyTo` в сообщении `CreateSequence` совпадают и используют [параметры ссылок] из ссылки на конечную точку `ReplyTo` в подтверждениях и сообщениях встречной последовательности.  
  
-   R1107: при установке двух встречных последовательностей с помощью механизма `Offer` сообщение `SequenceAcknowledgement` и сообщения приложения во встречных последовательностях должны отправляться по ссылке на конечную точку `ReplyTo` в сообщении `CreateSequence`.  
  
-   R1108: при установке двух встречных последовательностей с помощью механизма "Offer" свойство `[address]` дочернего элемента ссылки на конечную точку `wsrm:AcksTo` элемента `wsrm:Accept` в сообщении `CreateSequenceResponse` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.  
  
-   R1109: при установке двух встречных последовательностей с помощью механизма `Offer` сообщения, отправленные инициатором, и подтверждения на сообщения респондента должны отправляться по одной и той же ссылке на конечную точку.  
  
     В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] протокол WS-Reliable Messaging используется для установки надежных сеансов между инициатором и респондентом. Реализация протокола WS-Reliable Messaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает создание надежного сеанса для односторонней связи, обмена запросами и ответами и для полнодуплексного обмена сообщениями. WS-Reliable Messaging `Offer` с помощью механизма `CreateSequence` / `CreateSequenceResponse` позволяет устанавливать две коррелированные встречные последовательности и обеспечивает протокол сеанса, которая подходит для всех конечных точках обмена сообщениями. Поскольку платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] гарантирует безопасность таких сеансов, включая сквозную защиту для обеспечения целостности сеанса, она позволяет проверять, что сообщения, предназначенные одной и той же стороне, достигнут одной и той точки назначения. Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений. Таким образом, ограничения R1104, R1105 и R1108 относятся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
  
-   B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к возникновению ошибки и обращается к порядковые номера не выше, чем `xs:long`максимальное значение включительно, 9223372036854775807.  
  
-   B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создает пустой последним сообщением с URI действия http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
-   B1203: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сообщение получается и отправляется с заголовком последовательности, содержащим элемент `LastMessage`, при условии, что значение универсального кода ресурса (URI) действия не равно http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
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
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в качестве механизма поддержки активности используется заголовок `AckRequested`. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создается необязательный элемент `MessageNumber`. При получении сообщения с заголовком `AckRequested`, содержащим элемент `MessageNumber`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] игнорирует значение элемента `MessageNumber`, как показано в следующем примере.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>Заголовок SequenceAcknowledgement  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для передачи подтверждений последовательностей протокола WS-Reliable Messaging используются сообщения приложений.  
  
-   R1401: при установке двух встречных последовательностей с помощью механизма `Offer` заголовок `SequenceAcknowledgement` может включаться в любое сообщение приложения, передаваемое определенному получателю.  
  
-   B1402: когда в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] необходимо создать подтверждение перед получением любых сообщений последовательности (например, чтобы соответствовать требованиям сообщения `AckRequested`), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает заголовок `SequenceAcknowledgement`, содержащий диапазон 0-0, как показано в следующем примере.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются заголовки `SequenceAcknowledgement`, содержащие элемент `Nack`, но поддерживаются элементы `Nack`.  
  
### <a name="ws-reliablemessaging-faults"></a>Ошибки протокола WS-ReliableMessaging  
 Ниже приведен список ограничений, относящихся к реализации ошибок протокола WS-Reliable Messaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B1501: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются ошибки `MessageNumberRollover`.  
  
-   B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может создать конечную точку `CreateSequenceRefused` ошибок, как описано в спецификации.  
  
-   B1503:When конечной точки службы достигает этого значения подключения и не может обработать новые подключения, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к возникновению дополнительного `CreateSequenceRefused` код, ошибки `netrm:ConnectionLimitReached`, как показано в следующем примере.  
  
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
 Поскольку протокол WS-Reliable Messaging использует протокол WS-Addressing, реализация WS-Reliable Messaging [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может создавать и передавать ошибки WS-Addressing. В этом разделе описаны ошибки WS-Addressing, которые среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]явным образом создает и передает на уровне WS-Reliable Messaging.  
  
-   B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] формирует ошибку, требуется адресация заголовок сообщения в том случае, если выполняется одно из следующих действий:  
  
    -   в сообщении отсутствуют заголовки `Sequence` и `Action`;  
  
    -   в сообщении `CreateSequence` отсутствует заголовок `MessageId`.  
  
    -   в сообщении `CreateSequence` отсутствует заголовок `ReplyTo`.  
  
-   B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] формирует ошибку, действие не поддерживается в ответ на сообщение, которое отсутствует `Sequence` заголовок и имеет `Action` заголовок, который не распознается в спецификации WS-Reliable Messaging.  
  
-   B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] формирует ошибку, конечная точка недоступна для указания, что конечной точки не обрабатывает последовательность на основании проверки `CreateSequence` заголовков адресов в сообщении.  
  
## <a name="protocol-composition"></a>Сочетаемость протокола  
  
### <a name="composition-with-ws-addressing"></a>Сочетаемость с WS-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации консорциума W3C по протоколу WS-Addressing версии 1.0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].  
  
 Поскольку в спецификации протокола WS-Reliable Messaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   R2101: как можно использовать с WS-Reliable Messaging WS-Addressing 2004/08 и WS-Addressing 1.0.  
  
-   Необходимо использовать одну версию WS-Addressing R2102:A во всей заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью `wsrm:Offer` механизм.  
  
### <a name="composition-with-soap"></a>Сочетаемость с SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает использование с протоколом WS-Reliable Messaging как версии SOAP 1.1, так и версии SOAP 1.2.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Сочетаемость с WS-Security и WS-SecureConversation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает защиту последовательностей WS-Reliable Messaging с помощью безопасного транспорта (HTTPS) и совместимости с протоколами WS-Security и WS-Secure Conversation. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   R2301: для защиты целостности последовательности WS-Reliable Messaging в дополнение к целостности и конфиденциальности отдельных сообщений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует, что необходимо использовать WS-Secure Conversation.  
  
-   R2302:AWS-Secure Conversation должен быть установлен до установки последовательностях WS-Reliable Messaging.  
  
-   R2303: если время существования последовательности WS-Reliable Messaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.  
  
-   B2304:ws-последовательности системы надежного обмена сообщениями или пару коррелированные встречные последовательности всегда привязан к одного сеанса WS-SecureConversation.  
  
     Источник в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `wsse:SecurityTokenReference`, используя раздел расширения элемента заголовка в сообщении `CreateSequence`.  
  
-   Сочетание с WS-Secure Conversation R2305:When `CreateSequence` сообщение должно содержать `wsse:SecurityTokenReference` элемента.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Утверждение WS-Reliable Messaging WS-Policy  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] утверждение WS-Reliable Messaging WS-Policy `wsrm:RMAssertion` используется для описания возможностей конечных точек. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B3001: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] к элементам `wsrm:RMAssertion` прикрепляется проверочное утверждение WS-Policy `wsdl:binding`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает вложения в элементы `wsdl:binding` и `wsdl:port`.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает следующие дополнительные свойства утверждения WS-Reliable Messaging и реализует контроль над ними через элемент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:  
  
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
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует расширяемость WS-Reliable Messaging, чтобы обеспечить более строгий контроль над потоком сообщений последовательности.  
  
 Включить управление потоком, задав `ReliableSessionBindingElement` `FlowControlEnabled``bool` свойства `true`. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B4001: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `netrm:BufferRemaining`, используя возможности расширения элемента заголовка `SequenceAcknowledgement`.  
  
-   B4002: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требует наличия элемента `netrm:BufferRemaining` в заголовке `SequenceAcknowledgement`, как показано в следующем примере.  
  
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
  
-   B4003: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется элемент `netrm:BufferRemaining`, чтобы задать количество новых сообщений, которые точка назначения системы надежного обмена сообщениями может поместить в буфер.  
  
-   B4004: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] надежного обмена сообщениями службы регулирует количество сообщений, передаваемых при приложения назначения надежного обмена сообщениями не может быстро получать сообщения. Точка назначения системы надежного обмена сообщениями помещает сообщения в буфер, и значение элемента снижается до 0.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает целые значения элемента `netrm:BufferRemaining` в интервале от 0 до 4096 включительно и считывает целые значения в интервале от 0 до максимального значения типа `xs:int` (`maxInclusive`, 214748364) включительно.  
  
## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями  
 В этом разделе описана работа среды [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании протокола WS-Reliable Messaging для различных шаблонов обмена сообщениями. Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:  
  
-   неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;  
  
-   адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.  
  
### <a name="one-way-non-addressable-initiator"></a>Односторонний неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используются HTTP-запросы для передачи всех сообщений от диспетчеров ресурсов в RMD и HTTP-ответы для передачи всех сообщений от RMD к диспетчеру ресурсов.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` без предложений. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` нет предложений перед созданием последовательности. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос `CreateSequence` сообщением `CreateSequenceResponse`.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает подтверждения при ответе на все сообщения, кроме сообщения `CreateSequence` и сообщений об ошибках. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создает отдельное подтверждение в HTTP-ответе для сообщений последовательности и сообщений `AckRequested`.  
  
#### <a name="terminatesequence-message"></a>Сообщение TerminateSequence  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сообщение `TerminateSequence` рассматривается как односторонняя операция, т.е. HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
### <a name="one-way-addressable-initiator"></a>Односторонний адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями через один входящий и один исходящий канал HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP-запросы. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` без предложений. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` нет предложений перед созданием последовательности. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequenceResponse` в HTTP-запросе с помощью ссылки на конечную точку `ReplyTo`.  
  
### <a name="duplex-addressable-initiator"></a>Дуплексный адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон полностью асинхронного двустороннего обмена сообщениями с использованием двух последовательностей через входящий и исходящий канал HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP-запросы. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением. Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет сообщение `CreateSequenceResponse` в HTTP-запросе, направленном в конечную точку `CreateSequence` `ReplyTo`.  
  
#### <a name="sequence-lifetime"></a>Время существования последовательности  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] две последовательности рассматриваются в качестве одного полнодуплексного сеанса.  
  
 После разрыва одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает, что удаленная точка доступа вызовет разрыв в обеих последовательностях. После чтения разрыва в одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вызывает разрывы в обеих последовательностях.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности. И наоборот, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.  
  
### <a name="request-reply-non-addressable-initiator"></a>Обмен сообщениями запрос-ответ, неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями «запрос-ответ» с использованием двух последовательностей через один канал HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует HTTP-запросы для передачи сообщений последовательности запросов и HTTP-ответы для передачи сообщений последовательности ответов.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением. Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос `CreateSequence` сообщением `CreateSequenceResponse`.  
  
#### <a name="one-way-message"></a>Односторонний обмен сообщениями  
 Для реализации протокола одностороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает отдельное сообщение `SequenceAcknowledgement` в HTTP-ответе. Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
#### <a name="two-way-messages"></a>Двусторонний обмен сообщениями  
 Для реализации протокола двустороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает сообщение последовательности ответов в HTTP-ответе. Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
 Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.  
  
#### <a name="retrying-replies"></a>Повторные попытки ответов  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для обеспечения корреляции между сообщениями протокола двустороннего обмена сообщениями используется корреляция между HTTP-запросами и ответами. Поэтому инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не прекращает попытки отправки сообщения последовательности запросов в случае подтверждения этого сообщения, а дожидается HTTP-ответа, содержащего подтверждение, пользовательское сообщение или ошибку. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] повторяет в HTTP-запросе ответы на запрос, с которым коррелирует этот ответ.  
  
#### <a name="lastmessage-exchange"></a>Обмен сообщениями LastMessage  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает последнее сообщение с пустым телом в HTTP-запросе. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает ответ, но не учитывает само ответное сообщение. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос с последним пустым сообщением последовательности ответом с последним пустым сообщением последовательности.  
  
 Если респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] получает последнее сообщение, в котором значение универсального кода ресурса (URI) действия отлично от http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает последним сообщением. В случае протокола двустороннего обмена сообщениями последнее сообщение содержит сообщение приложения, а в случае протокола одностороннего обмена сообщениями последнее сообщение будет пустым.  
  
 Для респондента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требуется подтверждение на ответ с последним пустым сообщением последовательности.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 Когда на все запросы получен допустимый ответ, инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает сообщение последовательности запросов `TerminateSequence` в HTTP-запросе. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает ответ, но не учитывает само ответное сообщение. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на сообщение `TerminateSequence` последовательности запроса сообщением `TerminateSequence` последовательности запроса.  
  
 В обычной последовательности отключения оба сообщения `TerminateSequence` содержат полный набор `SequenceAcknowledgement`.  
  
### <a name="requestreply-addressable-initiator"></a>Обмен сообщениями запрос-ответ, адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон обмена сообщениями «запрос-ответ» с использованием двух последовательностей через входящий и исходящий канал HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP-запросы. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением. Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет сообщение `CreateSequenceResponse` в HTTP-запросе, направленном в конечную точку `CreateSequence` `ReplyTo`.  
  
#### <a name="requestreply-correlation"></a>Корреляция запросов и ответов  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что все сообщения с запросами приложения содержат значение `MessageId` и ссылку на конечную точку `ReplyTo`. Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] применяет ссылку на конечную точку `CreateSequence` сообщения `ReplyTo` для каждого сообщения с запросом приложения. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует, чтобы все сообщения входящих запросов содержали значения `MessageId` и `ReplyTo`. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что значения универсальных кодов ресурсов (URI) для ссылки на конечную точку в сообщении `CreateSequence` и во всех сообщениях запросов приложения идентичны.
