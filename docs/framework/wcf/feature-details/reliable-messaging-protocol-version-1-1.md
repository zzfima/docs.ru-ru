---
title: Протокол надежного обмена сообщениями, версия 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 8ff02bc6953ec1e5030dd0b592a352b7e23ab0d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="reliable-messaging-protocol-version-11"></a>Протокол надежного обмена сообщениями, версия 1,1
В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для протокола WS-ReliableMessaging протокола февраля 2007 г. (версия 1.1), необходимые для взаимодействия с использованием транспорта HTTP. WCF соответствует спецификации WS-ReliableMessaging с определенными ограничениями и пояснениями, описанными далее в этом разделе. Обратите внимание, что реализуется начиная с версии 1.1 протокола WS-ReliableMessaging [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].  
  
 WS-ReliableMessaging февраля 2007 г. протокол реализуется в WCF с <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Для удобства объяснения в этом разделе используются следующие роли:  
  
-   инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;  
  
-   респондент: служба, получающая запросы инициатора.  
  
 В этом документе используются префиксы и пространства имен, описанные в следующей таблице.  
  
|Префикс|Пространство имен|  
|-|-|  
|wsrm|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|wsrmp|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|netrmp|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|wsp|(WS-Policy 1.2 или WS-Policy 1.5)|  
  
## <a name="messaging"></a>Обмен сообщениями  
  
### <a name="sequence-creation"></a>Создание последовательности  
 Реализует WCF `CreateSequence` и `CreateSequenceResponse` последовательности сообщений для установления надежного обмена сообщениями. Действуют следующие ограничения.  
  
-   B1101: Инициатор WCF использует ту же ссылку конечной точки, как `CreateSequence` сообщения `ReplyTo`, `AcksTo` и `Offer/Endpoint`.  
  
-   R1102: адреса ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь идентичные строковые представления, чтобы они совпадали на уровне октетов.  
  
    -   Респондент WCF проверяет, что URI части `AcksTo`, `ReplyTo` и `Endpoint` идентичны ссылки на конечные точки перед созданием последовательности.  
  
-   R1103: ссылки на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.  
  
    -   WCF не применяет принудительно, но предполагается, что ссылка параметры `AcksTo`, `ReplyTo` и `Offer/Endpoint` ссылок на `CreateSequence` идентичны и используются параметры `ReplyTo` ссылки на конечную точку для подтверждениях и сообщениях встречной последовательности.  
  
-   B1104: Инициатор WCF не создает необязательный `Expires` или `Offer/Expires` элемент в `CreateSequence` сообщения.  
  
-   B1105: При доступе к `CreateSequence` сообщение, отвечающая сторона WCF использует `Expires` значение в `CreateSequence` элемент как `Expires` значение в `CreateSequenceResponse` элемент. В противном случае респондент WCF считывает и игнорирует `Expires` и `Offer/Expires` значения.  
  
-   B1106: При доступе к `CreateSequenceResponse` сообщения WCF инициатора считывает необязательное `Expires` значение, но не используется.  
  
-   B1107: Инициатор WCF и отвечающее устройство всегда создают необязательный `IncompleteSequenceBehavior` элемент в `CreateSequence/Offer` и `CreateSequenceResponse` элементы.  
  
-   B1108: WCF использует только `DiscardFollowingFirstGap` и `NoDiscard` значения в `IncompleteSequenceBehavior` элемент.  
  
    -   Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.  
  
-   B1109: Если `CreateSequence` содержит `Offer` элемент, одним из способов WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceResponse` без `Accept` элемента.  
  
-   B1110: Если респондент отклоняет предложенную последовательность, инициатор WCF ошибках последовательность.  
  
-   B1111: Если `CreateSequence` не содержит `Offer` элемент, двустороннее WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceRefused` ошибки.  
  
-   R1112: при установке с помощью механизма `Offer` двух встречных последовательностей, свойство `[address]` ссылки на конечную точку `CreateSequenceResponse/Accept/AcksTo` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.  
  
-   R1113: при установке с помощью механизма `Offer` двух встречных последовательностей, все сообщения от инициатора к респонденту в обеих последовательностях должны отправляться по одной и той же ссылке на конечную точку.  
  
 WCF использует WS-ReliableMessaging для установки надежных сеансов между инициатором и респондентом. Реализация WS-ReliableMessaging, WCF обеспечивает создание надежного сеанса для односторонней связи, запрос ответ и полный двустороннего обмена сообщениями. Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями. Поскольку WCF гарантирует безопасность таких сеансов, включая защиты от начала до конца для обеспечения целостности сеанса, это целесообразно, чтобы убедиться, что сообщения, предназначенные для той же стороне доставлены в одном месте назначения. Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений. Таким образом R1102, R1112 и R1113 ограничения для WCF.  
  
 Пример сообщения `CreateSequence`.  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>  
    <wsa:ReplyTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>   
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>  
      </wsrm:AcksTo>  
      <wsrm:Offer>  
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>  
        <wsrm:Endpoint>  
          <wsa:Address>http://Business456.com/clientA</wsa:Address>  
        </wsrm:Endpoint>  
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      </wsrm:Offer>  
    </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 Пример сообщения `CreateSequenceResponse`.  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      <wsrm:Accept>  
        <wsrm:AcksTo>  
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>  
        </wsrm:AcksTo>  
      </wsrm:Accept>  
    </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="closing-a-sequence"></a>Закрытие последовательности  
 WCF использует `CloseSequence` и `CloseSequenceResponse` сообщений для завершения инициативе источника системы надежного обмена сообщениями. Назначения надежного обмена сообщениями WCF не инициирует завершение работы и Источник надежного обмена сообщениями WCF не поддерживает выключение инициируемое точкой назначения надежного обмена сообщениями. Действуют следующие ограничения.  
  
-   B1201: Источник надежного обмена сообщениями WCF всегда отправляет `CloseSequence` сообщение закрытия последовательности.  
  
-   B1202: источник системы надежного обмена сообщениями перед отправкой сообщения `CloseSequence` ждет подтверждения от всех сообщений последовательности.  
  
-   B1203: источник системы надежного обмена сообщениями всегда включает необязательный элемент `LastMsgNumber`, если в последовательности есть хотя бы одно сообщение.  
  
-   R1204: точка назначения системы надежного обмена сообщениями не должна инициировать закрытие последовательности путем отправки сообщения `CloseSequence`.  
  
-   B1205: после получения `CloseSequence` сообщение, Источник надежного обмена сообщениями WCF считает, что последовательность неполными и отправляет ошибку.  
  
 Пример сообщения `CloseSequence`.  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
    </wsrm:CloseSequence>  
  </s:Body>  
</s:Envelope>  
Example CloseSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:CloseSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence-termination"></a>Завершение последовательности  
 WCF в основном используется `TerminateSequence/TerminateSequenceResponse` подтверждения после завершения `CloseSequence/CloseSequenceResponse` подтверждения. Назначения надежного обмена сообщениями WCF не инициирует завершение и источник системы надежного обмена сообщениями не поддерживает завершение инициируемое точкой назначения надежного обмена сообщениями. Действуют следующие ограничения.  
  
-   B1301: Инициатор WCF только отправляет `TerminateSequence` сообщение после успешного завершения `CloseSequence/CloseSequenceResponse` подтверждения.  
  
-   R1302: WCF проверяет, что `LastMsgNumber` элемент одинаков во всех `CloseSequence` и `TerminateSequence` сообщений для заданной последовательности. Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.  
  
-   B1303: при получении сообщения `TerminateSequence` после подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями отправляет в ответ сообщение `TerminateSequenceResponse`. Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.  
  
-   B1304: При получении `TerminateSequence` сообщений до `CloseSequence/CloseSequenceResponse` подтверждения назначения надежного обмена сообщениями WCF отвечает `TerminateSequenceResponse` сообщения. Если точка назначения системы надежного обмена сообщениями определяет, что в последовательности нет противоречий, она, прежде чем высвободить ресурсы, ждет в течение времени, заданного точкой назначения приложения, чтобы клиент мог получить последнее подтверждение. В противном случае точка назначения системы надежного обмена сообщениями сразу же высвобождает ресурсы и сообщает точке назначения приложения, что последовательность завершена, но не гарантированно, вызывая для этого событие `Faulted`.  
  
 Пример сообщения `TerminateSequence`.  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
      </wsrm:TerminateSequence>  
  </s:Body>  
</s:Envelope>  
Example TerminateSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:TerminateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequences"></a>Последовательности  
 Ниже приведен список ограничений, относящихся к последовательностям.  
  
-   Создает B1401:WCF и обращается к порядковых номеров, не превышает `xs:long`максимальное значение включительно, 9223372036854775807.  
  
 Пример заголовка `Sequence`.  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a>Запрос подтверждения  
 WCF использует `AckRequested` заголовок как механизм поддержания активности.  
  
 Пример заголовка `AckRequested`.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 WCF использует механизм «делает обратной» для передачи подтверждений последовательностей в WS-Reliable Messaging. Действуют следующие ограничения.  
  
-   R1601: При установке двух встречных последовательностей, устанавливаются с помощью `Offer` механизм, `SequenceAcknowledgement` заголовок может быть включено в любое сообщение приложения, передаваемых предполагаемому получателю. Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.  
  
-   B1602: WCF не создает `SequenceAcknowledgement` заголовков, содержащих `Nack` элементов. WCF проверяет, каждая из которых `Nack` элемент содержит порядковый номер, но в противном случае значение не учитывает `Nack` элементом и значением.  
  
 Пример заголовка `SequenceAcknowledgement`.  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a>Ошибки протокола WS-ReliableMessaging  
 Ниже приведен список ограничений, относящихся к реализации WCF ошибки протокола WS-ReliableMessaging. Действуют следующие ограничения.  
  
-   B1701: WCF не создает `MessageNumberRollover` ошибок.  
  
-   B1702: В SOAP 1.2, когда конечной точки службы достигает этого значения подключения и не может обработать новые подключения, WCF создает вложенный `CreateSequenceRefused` код, ошибки `netrm:ConnectionLimitReached`, как показано в следующем примере.  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>  
  </s:Header>  
  <s:Body>  
    <s:Fault>  
      <s:Code>  
        <s:Value>s:Receiver</s:Value>  
        <s:Subcode>  
          <s:Value>wsrm:CreateSequenceRefused</s:Value>  
          <s:Subcode>  
            <s:Value>netrm:ConnectionLimitReached</s:Value>  
          </s:Subcode>  
        </s:Subcode>  
      </s:Code>  
      <s:Reason>  
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>  
      </s:Reason>  
    </s:Fault>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="ws-addressing-faults"></a>Ошибки WS-Addressing  
 Так как WS-ReliableMessaging использует протокол WS-Addressing, реализация WS-ReliableMessaging, WCF может создавать и передавать ошибки WS-Addressing. В этом разделе описаны ошибки WS-Addressing, которые WCF явным образом создает и передает на уровне WS-ReliableMessaging:  
  
-   B1801:WCF создает и передает `Message Addressing Header Required` сбоя при выполнении одного из следующих действий:  
  
    -   в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;  
  
    -   в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;  
  
    -   в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.  
  
-   B1802:WCF создает и передает `Endpoint Unavailable` ошибки для указания отсутствует конечная точка ожидает передачи данных, который может обрабатывать последовательности, основанной на изучение заголовки адресации в `CreateSequence` сообщения.  
  
## <a name="protocol-composition"></a>Сочетаемость протокола  
  
### <a name="composition-with-ws-addressing"></a>Сочетаемость с WS-Addressing  
 WCF поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации W3C WS-Addressing 1.0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].  
  
 Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing. Ниже приведен список ограничений, относящихся к WCF:  
  
-   R2101: с протоколом WS-ReliableMessaging можно использовать как версию WS-Addressing 2004/08, так и версию WS-Addressing 1.0.  
  
-   R2102: в рамках заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью механизма `Offer`, следует использовать только одну версию WS-Addressing.  
  
### <a name="composition-with-soap"></a>Сочетаемость с SOAP  
 WCF поддерживает использование SOAP 1.1 и SOAP 1.2 с WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Сочетаемость с WS-Security и WS-SecureConversation  
 WCF обеспечивает защиту последовательностей WS-ReliableMessaging с помощью безопасного транспорта (HTTPS), сочетаемость с WS-Security и сочетаемость с WS-Secure Conversation. Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно. Ниже приведен список ограничений, относящихся к WCF:  
  
-   R2301: Для защиты целостности последовательности WS-ReliableMessaging, помимо целостности и конфиденциальности отдельных сообщений, WCF требуется должен использоваться WS-Secure Conversation.  
  
-   R2302:AWS-Secure Conversation должен быть установлен до установки последовательностях WS-ReliableMessaging.  
  
-   R2303: если время существования последовательности WS-ReliableMessaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.  
  
-   B2304:ws-последовательности ReliableMessaging или пары коррелированные встречные последовательности всегда привязан к одного сеанса WS-SecureConversation.  
  
-   R2305: При создании WS-Secure Conversation респондент WCF требуется `CreateSequence` сообщение содержит `wsse:SecurityTokenReference` элемент и `wsrm:UsesSequenceSTR` заголовок.  
  
 Пример заголовка `UsesSequenceSTR`.  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a>Сочетаемость с сеансами SSL/TLS  
 WCF не поддерживает сочетаемость с сеансами SSL/TLS.  
  
-   B2401: WCF не создает `wsrm:UsesSequenceSSL` заголовок.  
  
-   R2402: Инициатор С надежного обмена сообщениями не должен отправлять `CreateSequence` сообщений с `wsrm:UsesSequenceSSL` заголовок, чтобы респондент WCF.  
  
### <a name="composition-with-ws-policy"></a>Сочетаемость с WS-Policy  
 WCF поддерживает две версии протокола WS-Policy: WS-Policy 1.2 и WS-Policy 1.5.  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a>Утверждение WS-ReliableMessaging WS-Policy  
 WCF использует утверждение WS-ReliableMessaging WS-Policy `wsrm:RMAssertion` для описания возможностей конечных точек. Ниже приведен список ограничений, относящихся к WCF:  
  
-   B3001: Присоединяет WCF `wsrmn:RMAssertion` утверждение WS-Policy для `wsdl:binding` элементов. WCF поддерживает вложения в `wsdl:binding` и `wsdl:port` элементы.  
  
-   B3002: WCF никогда не приводит к возникновению ошибки `wsp:Optional` тег.  
  
-   B3003: При доступе к `wsrmp:RMAssertion` утверждение WS-Policy WCF игнорирует `wsp:Optional` теги и трактует политику WS-RM как обязательную.  
  
-   R3004: Поскольку WCF не составить с сеансами SSL/TLS, WCF не принимает политики, задающие `wsrmp:SequenceTransportSecurity`.  
  
-   B3005: WCF всегда приводит к возникновению ошибки `wsrmp:DeliveryAssurance` элемента.  
  
-   B3006: WCF всегда указывает `wsrmp:ExactlyOnce` гарантии доставки.  
  
-   B3007: WCF приводит к возникновению ошибки и считывает следующие свойства утверждения WS-ReliableMessaging и реализует контроль над ними в WCF`ReliableSessionBindingElement`:  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     Пример `RMAssertion`.  
  
    ```xml  
    <wsrmp:RMAssertion>  
      <wsp:Policy>  
        <wsrmp:SequenceSTR/>  
        <wsrmp:DeliveryAssurance>  
          <wsp:Policy>  
            <wsrmp:ExactlyOnce/>  
            <wsrmp:InOrder/>  
          </wsp:Policy>  
        </wsrmp:DeliveryAssurance>  
      </wsp:Policy>  
      <netrmp:InactivityTimeout Milliseconds="600000"/>  
      <netrmp:AcknowledgementInterval Milliseconds="200"/>  
    </wsrmp:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliablemessaging-extension"></a>Расширение WS-ReliableMessaging для управления потоком  
 WCF использует расширяемость WS-ReliableMessaging для обеспечения более строгий контроль над потоком последовательности сообщений.  
  
 Включить управление потоком, задав `ReliableSessionBindingElement` `FlowControlEnabled``boolean` свойства `true`. Ниже приведен список ограничений, относящихся к WCF:  
  
-   B4001: Если включена надежного обмена сообщениями потока управления, WCF приводит к возникновению ошибки `netrm:BufferRemaining` элемент расширения элемента `SequenceAcknowledgement` заголовок, как показано в следующем примере.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: Даже в том случае, если включена надежного обмена сообщениями потока управления, WCF не требует `netrm:BufferRemaining` элемент в `SequenceAcknowledgement` заголовок.  
  
-   B4003: Назначения надежного обмена сообщениями WCF использует `netrm:BufferRemaining` для указания того, сколько новых сообщений, его размер буфера.  
  
-   Включить B4004:When надежного обмена сообщениями потока управления, Источник надежного обмена сообщениями WCF использует значение `netrm:BufferRemaining` регулирования передачу сообщений.  
  
-   B4005: WCF формирует `netrm:BufferRemaining` integer значения от 0 до 4096 включительно и считывает целые значения в диапазоне от 0 и `xs:int` `maxInclusive` значение 214748364 включительно.  
  
## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями  
 Этот раздел описывает поведение WCF, при использовании протокола WS-ReliableMessaging для различных шаблонов обмена сообщениями. Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:  
  
-   неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;  
  
-   адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.  
  
### <a name="one-way-non-addressable-initiator"></a>Односторонний неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Передает инициатора WCF `CreateSequence` сообщений которых не `Offer` элемент в HTTP-запросе и ожидает `CreateSequenceResponse` сообщение HTTP-ответе. Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений нет `Accept` элемент в HTTP-ответе.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Инициатор WCF обрабатывает подтверждения при ответе на все сообщения, за исключением `CreateSequence` сообщений и сообщений об ошибках. Респондент WCF всегда передает отдельное подтверждение в HTTP-ответе на все последовательности и `AckRequested` сообщений.  
  
#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence  
 Инициатор WCF передает `CloseSequence` сообщение HTTP-запроса и ожидает `CreateSequenceResponse` сообщение HTTP-ответе. Респондент WCF передает `CloseSequenceResponse` сообщение HTTP-ответе.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 Инициатор WCF передает `TerminateSequence` сообщение HTTP-запроса и ожидает `TerminateSequenceResponse` сообщение HTTP-ответе. Респондент WCF передает `TerminateSequenceResponse` сообщение HTTP-ответе.  
  
### <a name="one-way-addressable-initiator"></a>Односторонний адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и один исходящий канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщений нет `Offer` элемент HTTP-запроса. Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений нет `Accept` элемент HTTP-запроса.  
  
### <a name="duplex-addressable-initiator"></a>Дуплексный адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет полностью асинхронного, двустороннего обмена сообщениями с использованием двух последовательностей через один входящий и один исходящий канал HTTP. Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса. Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемента, после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемента.  
  
#### <a name="sequence-lifetime"></a>Время существования последовательности  
 WCF две последовательности рассматриваются в качестве одного полностью двустороннего сеанса.  
  
 При создании ошибки разрыва одной последовательности, WCF предполагает, что Удаленная конечная точка разрыв в обеих последовательностях. После чтения разрыва одной последовательности, WCF ошибках обеих последовательностях.  
  
 WCF можно закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности. И наоборот WCF может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет одностороннее и шаблон обмена сообщениями запрос ответ, с использованием двух последовательностей через один канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент в HTTP-запросе и ожидает `CreateSequenceResponse` сообщение HTTP-ответе. Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент в HTTP-ответе.  
  
#### <a name="one-way-message"></a>Односторонний обмен сообщениями  
 Для успешного завершения односторонний обмен сообщениями WCF инициатора передает сообщение последовательности запросов в HTTP-запросе и получает отдельное `SequenceAcknowledgement` сообщение HTTP-ответе. Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.  
  
 Респондент WCF может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
#### <a name="two-way-messages"></a>Двусторонний обмен сообщениями  
 Для реализации протокола двустороннего сообщений exchange, инициатор WCF передает сообщение последовательности запросов в HTTP-запросе и получает сообщение последовательности ответов в HTTP-ответе. Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.  
  
 Респондент WCF может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
 Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.  
  
#### <a name="retrying-replies"></a>Повторные попытки ответов  
 WCF использует корреляцию запросов и ответов HTTP для корреляции протокола двустороннего сообщений exchange. По этой причине инициатора WCF не прекращает попытки сообщение последовательности запросов, когда подтверждается сообщение последовательности запросов а дожидается HTTP-ответа, содержащего `SequenceAcknowledgement`, ответ приложения или ошибки. Респондент WCF повторяет ответы HTTP-ответе запроса, с которой связан этот ответ.  
  
#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence  
 После получения всех сообщений последовательности ответов и подтверждений для всех сообщений последовательности одним из способов запроса, инициатором WCF передает `CloseSequence` сообщение последовательности запросов в HTTP-запросе и ожидает `CloseSequenceResponse` в HTTP-ответе.  
  
 Закрытие последовательности запросов неявным образом закрывает последовательность ответов. Это означает, что инициатор WCF включает последнее подтверждение последовательности ответа `SequenceAcknowledgement` на `CloseSequence` сообщение и последовательности ответов нет `CloseSequence` exchange.  
  
 Респондент WCF обеспечивает все ответы подтверждения и передает `CloseSequenceResponse` сообщение HTTP-ответе.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 После получения `CloseSequenceResponse` передает сообщения WCF инициатора `TerminateSequence` сообщение последовательности запросов в HTTP-запросе и ожидает `TerminateSequenceResponse` в HTTP-ответе.  
  
 Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов. Это означает, что инициатор WCF включает последнее подтверждение последовательности ответа `SequenceAcknowledgement` на `TerminateSequence` сообщение и последовательности ответов нет `TerminateSequence` exchange.  
  
 Респондент WCF передает `TerminateSequenceResponse` сообщение HTTP-ответе.  
  
### <a name="requestreply-addressable-initiator"></a>Обмен сообщениями запрос-ответ, адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон обмена сообщениями запрос ответ с использованием двух последовательностей через один входящий и один исходящий канал HTTP. Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса. Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемент после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемента.  
  
#### <a name="requestreply-correlation"></a>Корреляция запросов и ответов  
 Следующие действия относятся ко всем связанным запросам и ответам.  
  
-   WCF обеспечивает все сообщения запроса приложения содержат `ReplyTo` ссылки на конечную точку и `MessageId`.  
  
-   WCF применяется ссылка локальную конечную точку каждого сообщения с запросом приложения `ReplyTo`. Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.  
  
-   WCF обеспечивает сообщения, входящих запросов содержали `MessageId` и `ReplyTo`.  
  
-   WCF обеспечивает `ReplyTo` URI конечной точки ссылки всех сообщений запросов приложения соответствует ссылке локальную конечную точку, как определено ранее.  
  
-   WCF обеспечивает, что все ответы содержат правильные `RelatesTo` и `To` заголовки `wsa` правилам связывания запросов и ответов.
