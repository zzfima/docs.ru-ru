---
title: Протокол надежного обмена сообщениями, версия 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 6b8732e0b48797c219b53bb8bf70e1ba57e25c42
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55073230"
---
# <a name="reliable-messaging-protocol-version-11"></a>Протокол надежного обмена сообщениями, версия 1,1
В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для WS-ReliableMessaging протокола февраля 2007 г. (версия 1.1), необходимые для взаимодействия с использованием транспорта HTTP. WCF соответствует спецификации WS-ReliableMessaging с определенными ограничениями и пояснениями, описанными далее в этом разделе. Обратите внимание, что реализуется начиная с версии 1.1 протокола WS-ReliableMessaging [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].  
  
 WS-ReliableMessaging февраля 2007 г. протокол реализуется в WCF, <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Для удобства объяснения в этом разделе используются следующие роли:  
  
-   Инициатор: Клиент, инициирующий Создание последовательности сообщений WS-Reliable.  
  
-   Респондент: Служба, получающая запросы инициатора.  
  
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
 В WCF реализована `CreateSequence` и `CreateSequenceResponse` последовательности сообщений для установления надежный обмен сообщениями. Действуют следующие ограничения.  
  
-   B1101: Инициатор WCF использует одну и ту же ссылку конечной точки как `CreateSequence` сообщения `ReplyTo`, `AcksTo` и `Offer/Endpoint`.  
  
-   R1102: `AcksTo`, `ReplyTo` И `Offer/Endpoint` ссылается на конечную точку в `CreateSequence` сообщения должны иметь значения адресов идентичные строковые представления, таким образом, чтобы они совпадали на уровне октетов.  
  
    -   Респондент WCF проверяет, что часть URI `AcksTo`, `ReplyTo` и `Endpoint` идентичны ссылки на конечные точки перед созданием последовательности.  
  
-   R1103: `AcksTo`, `ReplyTo` И `Offer/Endpoint` ссылается на конечную точку в `CreateSequence` сообщения должны иметь тот же набор параметров ссылок.  
  
    -   WCF не применяет принудительно, но предполагается, что ссылочные параметры `AcksTo`, `ReplyTo` и `Offer/Endpoint` на конечные точки `CreateSequence` идентичны и используются параметры ссылки `ReplyTo` ссылки на конечную точку подтверждениях и сообщениях встречной последовательности.  
  
-   B1104: Инициатор WCF не создает необязательный `Expires` или `Offer/Expires` элемент в `CreateSequence` сообщения.  
  
-   B1105: При доступе к `CreateSequence` сообщение, отвечающее устройство WCF использует `Expires` значение в `CreateSequence` элемент как `Expires` значение в `CreateSequenceResponse` элемент. В противном случае респондент WCF считывает и игнорирует `Expires` и `Offer/Expires` значения.  
  
-   B1106: При доступе к `CreateSequenceResponse` сообщение, инициатор WCF считывает необязательное `Expires` значение, но не использует его.  
  
-   B1107: WCF-инициатор и отвечающее устройство всегда создают необязательный `IncompleteSequenceBehavior` элемент в `CreateSequence/Offer` и `CreateSequenceResponse` элементы.  
  
-   B1108: WCF использует только `DiscardFollowingFirstGap` и `NoDiscard` значения в `IncompleteSequenceBehavior` элемент.  
  
    -   Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.  
  
-   B1109: Если `CreateSequence` содержит `Offer` элемент, один из способов WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceResponse` без `Accept` элемент.  
  
-   B1110: Если респондент отклоняет предложенную последовательность, инициатор WCF ошибки последовательность.  
  
-   B1111: Если `CreateSequence` не содержит `Offer` элемент, двустороннее WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceRefused` сбоя.  
  
-   R1112: При установлении двух встречных последовательностей с помощью `Offer` механизм, `[address]` свойство `CreateSequenceResponse/Accept/AcksTo` ссылки на конечную точку должен соответствовать URI назначения из `CreateSequence` сообщения.  
  
-   R1113: При установлении двух встречных последовательностей с помощью `Offer` механизм, все сообщения в обеих последовательностях от инициатора к респонденту должны быть отправлены в одну и ту же ссылку конечной точки.  
  
 WCF использует WS-ReliableMessaging для установки надежных сеансов между инициатором и респондентом. Реализация WCF WS-ReliableMessaging обеспечивает создание надежного сеанса для односторонней связи, запрос ответ и полный двустороннего обмена сообщениями. Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями. Так как WCF гарантирует безопасность таких сеансов, включая защиту end-to-end для обеспечения целостности сеанса, целесообразно убедиться, что сообщения, предназначенные для той же стороне прибывают в том же месте назначения. Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений. Таким образом R1102 R1112 и R1113 ограничения на платформу WCF.  
  
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
 WCF использует `CloseSequence` и `CloseSequenceResponse` сообщения для завершения инициативе источника системы надежного обмена сообщениями. Назначение надежного обмена сообщениями WCF не инициируют завершение работы и Источник надежного обмена сообщениями WCF не поддерживает завершение работы системы надежного обмена сообщениями инициируемое точкой назначения. Действуют следующие ограничения.  
  
-   B1201: Источник надежного обмена сообщениями WCF всегда отправляет `CloseSequence` сообщения для закрытия последовательности.  
  
-   B1202: Источник системы надежного обмена сообщениями ожидает подтверждения перед отправкой полного диапазона всех сообщений последовательности `CloseSequence` сообщения.  
  
-   B1203: Источник системы надежного обмена сообщениями всегда включает необязательный `LastMsgNumber` элемент, если последовательность не содержит сообщения.  
  
-   R1204: Назначения системы надежного обмена сообщениями не должна инициировать, отправляя `CloseSequence` сообщения.  
  
-   B1205: При получении сообщения `CloseSequence` сообщение, источнику надежного обмена сообщениями WCF считает, что последовательность неполными и отправляет ошибку.  
  
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
 WCF в основном используется `TerminateSequence/TerminateSequenceResponse` подтверждение, после завершения `CloseSequence/CloseSequenceResponse` подтверждения. Назначение надежного обмена сообщениями WCF инициирует завершение последовательности, а источник системы надежного обмена сообщениями не поддерживает завершение инициируемое точкой назначения системы надежного обмена сообщениями. Действуют следующие ограничения.  
  
-   B1301: Инициатор WCF отправляет только `TerminateSequence` сообщения после успешного завершения `CloseSequence/CloseSequenceResponse` подтверждения.  
  
-   R1302: СРЕДА WCF проверяет, что `LastMsgNumber` элемента одинаков во всех `CloseSequence` и `TerminateSequence` сообщений для заданной последовательности. Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.  
  
-   B1303: При получении `TerminateSequence` сообщения после `CloseSequence/CloseSequenceResponse` подтверждения назначения системы надежного обмена сообщениями отвечает `TerminateSequenceResponse` сообщения. Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.  
  
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
  
-   Создает B1401:WCF и обращается к порядковые номера, не превышающие `xs:long`его максимального значения 9223372036854775807.  
  
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
 WCF использует «» подтверждений для подтверждений последовательностей в WS-Reliable Messaging. Действуют следующие ограничения.  
  
-   R1601: При установлении двух встречных последовательностей с помощью `Offer` механизм, `SequenceAcknowledgement` заголовка может быть включено в любое сообщение приложения предполагаемому получателю. Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.  
  
-   B1602: WCF не создает `SequenceAcknowledgement` заголовков, содержащих `Nack` элементов. WCF проверяет, что каждый `Nack` элемент содержит порядковый номер, но в противном случае игнорирует `Nack` элемент и значение.  
  
 Пример заголовка `SequenceAcknowledgement`.  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a>Ошибки протокола WS-ReliableMessaging  
 Ниже приведен список ограничений, относящихся к реализации ошибок WS-ReliableMessaging WCF. Действуют следующие ограничения.  
  
-   B1701: WCF не создает `MessageNumberRollover` ошибок.  
  
-   B1702: Через SOAP 1.2, когда конечная точка службы достигает достигается максимальное число подключений и не может обработать новые подключения, WCF создает вложенный `CreateSequenceRefused` код ошибки, `netrm:ConnectionLimitReached`, как показано в следующем примере.  
  
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
 Так как WS-ReliableMessaging использует WS-Addressing, реализация WCF WS-ReliableMessaging может создавать и передавать ошибки WS-Addressing. В этом разделе описаны ошибки WS-Addressing, которые WCF явным образом создает и передает на уровне WS-ReliableMessaging:  
  
-   B1801:WCF создает и передает `Message Addressing Header Required` сбоя при выполнении одного из следующих:  
  
    -   в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;  
  
    -   в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;  
  
    -   в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.  
  
-   B1802:WCF создает и передает `Endpoint Unavailable` сбоя для указания нет конечной точки прослушивания, который может обработать последовательность на основании проверки заголовков адресов в `CreateSequence` сообщения.  
  
## <a name="protocol-composition"></a>Сочетаемость протокола  
  
### <a name="composition-with-ws-addressing"></a>Сочетаемость с WS-Addressing  
 WCF поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и W3C WS-Addressing 1.0 рекомендации [WS-ADDR-CORE] и [WS-ADDR-SOAP].  
  
 Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing. Ниже приведен список ограничений, относящихся к WCF:  
  
-   R2101: С помощью WS-Reliable Messaging можно использовать как WS-Addressing 2004/08, так и WS-Addressing 1.0.  
  
-   R2102: Следует использовать одну версию WS-Addressing заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью `Offer` механизм.  
  
### <a name="composition-with-soap"></a>Сочетаемость с SOAP  
 WCF поддерживает использование протокола SOAP 1.1 и SOAP 1.2 с WS-Reliable Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Сочетаемость с WS-Security и WS-SecureConversation  
 WCF обеспечивает защиту последовательностей WS-ReliableMessaging с помощью безопасного транспорта (HTTPS), сочетаемость с WS-Security и WS-Secure Conversation. Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно. Ниже приведен список ограничений, относящихся к WCF:  
  
-   R2301: Для защиты целостности последовательности WS-ReliableMessaging в дополнение к целостности и конфиденциальности отдельных сообщений, WCF требует, что необходимо использовать WS-Secure Conversation.  
  
-   R2302:AWS-Secure Conversation должен быть установлен сеанс WS-ReliableMessaging перед установкой последовательностей.  
  
-   R2303: Если время существования последовательности WS-ReliableMessaging существования сеанса WS-Secure Conversation, превышает `SecurityContextToken` установить с помощью WS-Secure Conversation должен обновляться с помощью привязки обновления WS-Secure Conversation.  
  
-   B2304:ws-последовательность ReliableMessaging или пара встречных последовательностей всегда ограничены одним сеансом WS-SecureConversation.  
  
-   R2305: При использовании с WS-Secure Conversation, отвечающая сторона WCF требует, `CreateSequence` сообщение содержит `wsse:SecurityTokenReference` элемент и `wsrm:UsesSequenceSTR` заголовка.  
  
 Пример заголовка `UsesSequenceSTR`.  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a>Сочетаемость с сеансами SSL/TLS  
 WCF не поддерживает совместное использование с сеансами SSL/TLS:  
  
-   B2401: WCF не создает `wsrm:UsesSequenceSSL` заголовка.  
  
-   R2402: Надежного обмена сообщениями инициатор не должен отправлять `CreateSequence` сообщений с `wsrm:UsesSequenceSSL` заголовок, чтобы респондент WCF.  
  
### <a name="composition-with-ws-policy"></a>Сочетаемость с WS-Policy  
 WCF поддерживает две версии WS-Policy: WS-Policy 1.2 и WS-Policy 1.5.  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a>Утверждение WS-ReliableMessaging WS-Policy  
 WCF использует утверждение WS-Policy WS-ReliableMessaging `wsrm:RMAssertion` для описания возможностей конечных точек. Ниже приведен список ограничений, относящихся к WCF:  
  
-   B3001: WCF присоединяет `wsrmn:RMAssertion` утверждение WS-Policy для `wsdl:binding` элементов. WCF поддерживает вложения в `wsdl:binding` и `wsdl:port` элементы.  
  
-   B3002: WCF никогда не создает `wsp:Optional` тега.  
  
-   B3003: При доступе к `wsrmp:RMAssertion` утверждение WS-Policy, WCF игнорирует `wsp:Optional` тегов и считает политики WS-RM обязательным.  
  
-   R3004: Поскольку WCF не используются совместно с сеансами SSL/TLS, WCF не принимает политика, задающая `wsrmp:SequenceTransportSecurity`.  
  
-   B3005: WCF всегда создает `wsrmp:DeliveryAssurance` элемент.  
  
-   B3006: WCF всегда указывает `wsrmp:ExactlyOnce` гарантии доставки.  
  
-   B3007: WCF создает и считывает следующие свойства утверждения WS-ReliableMessaging и предоставляет контроль над ними на WCF`ReliableSessionBindingElement`:  
  
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
 WCF использует расширяемость WS-ReliableMessaging, чтобы обеспечить необязательно более строгий контроль над потоком последовательности сообщений.  
  
 Управление потоком можно включить, задав <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> свойства `true`. Ниже приведен список ограничений, относящихся к WCF:  
  
-   B4001: При включении надежного обмена сообщениями потока управления, WCF создает `netrm:BufferRemaining` элемент расширения элемента `SequenceAcknowledgement` заголовка, как показано в следующем примере.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: Даже при включении надежного обмена сообщениями потока управления WCF не требует `netrm:BufferRemaining` элемент `SequenceAcknowledgement` заголовка.  
  
-   B4003: Назначение надежного обмена сообщениями WCF использует `netrm:BufferRemaining` для указания того, сколько новых сообщений его размер буфера.  
  
-   Включен B4004:When надежного обмена сообщениями потока управления, Источник надежного обмена сообщениями WCF использует значение `netrm:BufferRemaining` для передачи сообщений.  
  
-   B4005: WCF создает `netrm:BufferRemaining` целое число значений в диапазоне от 0 до 4096 включительно и считывает целые значения между 0 и `xs:int`в `maxInclusive` значение 214748364 включительно.  
  
## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями  
 В этом разделе описывает поведение WCF, когда WS-ReliableMessaging используется для различных шаблонов обмена сообщениями. Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:  
  
-   Неадресуемый инициатор Инициатор расположен за брандмауэром; Респондент может отправлять сообщения инициатору только с HTTP-ответами.  
  
-   Адресуемый инициатор Инициатор и отвечающее устройство можно отправлять HTTP-запросов; Другими словами можно установить два встречных HTTP-подключения.  
  
### <a name="one-way-non-addressable-initiator"></a>Односторонний неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщение, не имеющий `Offer` элемент HTTP-запрос и ожидает, что `CreateSequenceResponse` сообщение на HTTP-ответа. Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщение, не имеющий `Accept` элемент на HTTP-ответа.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Инициатор WCF обрабатывает подтверждения при ответе на все сообщения, за исключением `CreateSequence` сообщений и сообщений об ошибках. Респондент WCF всегда передает отдельное подтверждение в HTTP-ответов все последовательности и `AckRequested` сообщений.  
  
#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence  
 Инициатор WCF передает `CloseSequence` сообщений HTTP-запрос и ожидает, что `CreateSequenceResponse` сообщение на HTTP-ответа. Респондент WCF передает `CloseSequenceResponse` сообщение на HTTP-ответа.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 Инициатор WCF передает `TerminateSequence` сообщений HTTP-запрос и ожидает, что `TerminateSequenceResponse` сообщение на HTTP-ответа. Респондент WCF передает `TerminateSequenceResponse` сообщение на HTTP-ответа.  
  
### <a name="one-way-addressable-initiator"></a>Односторонний адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и один исходящий канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщение, не имеющий `Offer` элемент HTTP-запроса. Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщение, не имеющий `Accept` элемент HTTP-запроса.  
  
### <a name="duplex-addressable-initiator"></a>Дуплексный адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет полностью асинхронные, двустороннего обмена сообщениями с использованием двух последовательностей через один входящий и один исходящий канал HTTP. Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса. Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемент, после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент.  
  
#### <a name="sequence-lifetime"></a>Время существования последовательности  
 WCF две последовательности рассматриваются в качестве одного полностью двустороннего сеанса.  
  
 После создания разрыва одной последовательности, WCF предполагает, что Удаленная конечная точка сбой обоих последовательностей. После чтения разрыва в одной последовательности, WCF создает ошибки обоих последовательностей.  
  
 WCF можно закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности. И наоборот WCF может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет одностороннее и шаблон обмена сообщениями типа запрос ответ, с использованием двух последовательностей через один канал HTTP. WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запрос и ожидает, что `CreateSequenceResponse` сообщение на HTTP-ответа. Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент на HTTP-ответа.  
  
#### <a name="one-way-message"></a>Односторонний обмен сообщениями  
 Чтобы успешно завершить односторонний обмен сообщениями, инициатор WCF передает сообщение последовательности запросов в HTTP-запрос и получает отдельное `SequenceAcknowledgement` сообщение на HTTP-ответа. Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.  
  
 Респондент WCF может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
#### <a name="two-way-messages"></a>Двусторонний обмен сообщениями  
 Для реализации протокола двустороннего сообщений exchange, инициатор WCF передает сообщение последовательности запросов в HTTP-запрос и получает сообщение последовательности ответов на HTTP-ответа. Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.  
  
 Респондент WCF может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
 Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.  
  
#### <a name="retrying-replies"></a>Повторные попытки ответов  
 WCF использует корреляцию запросов и ответов HTTP для корреляции протокола двустороннего обмена. По этой причине инициатора WCF не прекращает попытки отправки сообщение последовательности запросов, когда подтверждается сообщение последовательности запросов, но вместо этого при HTTP-ответа содержит `SequenceAcknowledgement`, ответ приложения или сбоя. Респондент WCF повторяет ответы на HTTP-ответа запроса, к которому связан этот ответ.  
  
#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence  
 После получения всех сообщений последовательности ответов и подтверждений для всех сообщений последовательности односторонний запрос, инициатор WCF передает `CloseSequence` сообщений для последовательности запросов в HTTP-запросе и ожидает, что `CloseSequenceResponse` на HTTP-ответа.  
  
 Закрытие последовательности запросов неявным образом закрывает последовательность ответов. Это означает, что инициатор WCF включает последнее подтверждение последовательности ответов `SequenceAcknowledgement` на `CloseSequence` сообщения и последовательности ответов нет `CloseSequence` exchange.  
  
 Респондент WCF все ответы и подтверждения ранее и передает `CloseSequenceResponse` сообщение на HTTP-ответа.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 После получения `CloseSequenceResponse` передает сообщение, инициатор WCF `TerminateSequence` сообщений для последовательности запросов в HTTP-запросе и ожидает, что `TerminateSequenceResponse` на HTTP-ответа.  
  
 Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов. Это означает, что инициатор WCF включает последнее подтверждение последовательности ответов `SequenceAcknowledgement` на `TerminateSequence` сообщения и последовательности ответов нет `TerminateSequence` exchange.  
  
 Респондент WCF передает `TerminateSequenceResponse` сообщение на HTTP-ответа.  
  
### <a name="requestreply-addressable-initiator"></a>Обмен сообщениями запрос-ответ, адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 WCF предоставляет шаблон обмена сообщениями типа запрос ответ с использованием двух последовательностей через один входящий и один исходящий канал HTTP. Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса. Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемент после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент.  
  
#### <a name="requestreply-correlation"></a>Корреляция запросов и ответов  
 Следующие действия относятся ко всем связанным запросам и ответам.  
  
-   WCF обеспечивает все сообщения запроса приложения содержат `ReplyTo` ссылки на конечную точку и `MessageId`.  
  
-   WCF применяет ссылку на локальную конечную точку как каждого сообщения с запросом приложения `ReplyTo`. Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.  
  
-   WCF обеспечивает все сообщения этой входящих запросов содержат `MessageId` и `ReplyTo`.  
  
-   WCF обеспечивает `ReplyTo` URI ссылки на конечную точку из всех сообщений запросов приложения соответствует ссылки локальной конечной точки, как было описано ранее.  
  
-   WCF гарантирует, что все ответы содержат правильные `RelatesTo` и `To` заголовки `wsa` правилам связывания запросов и ответов.
