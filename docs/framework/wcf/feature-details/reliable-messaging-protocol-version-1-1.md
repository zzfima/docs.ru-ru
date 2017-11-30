---
title: "Протокол надежного обмена сообщениями, версия 1,1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 98fe8ac04b7ac811802466cf63c58ea4cebd791e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-messaging-protocol-version-11"></a>Протокол надежного обмена сообщениями, версия 1,1
В этом разделе описаны особенности реализации в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] протокола WS-ReliableMessaging (версия 1.1 от февраля 2007 года), необходимого для взаимодействия с использованием транспорта HTTP. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] соблюдена спецификация WS-ReliableMessaging с определенными ограничениями и пояснениями, описанными далее в этом разделе. Обратите внимание, что реализуется начиная с версии 1.1 протокола WS-ReliableMessaging [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].  
  
 Версия протокола WS-ReliableMessaging от февраля 2007 г. реализована в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью класса <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
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
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализованы сообщения `CreateSequence` и `CreateSequenceResponse`, позволяющие установить последовательность системы надежного обмена сообщениями. Действуют следующие ограничения.  
  
-   B1101: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует одну и ту же ссылку в качестве конечных точек `CreateSequence`, `ReplyTo` и `AcksTo` в сообщении `Offer/Endpoint`.  
  
-   R1102: адреса ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь идентичные строковые представления, чтобы они совпадали на уровне октетов.  
  
    -   Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] перед созданием последовательности проверяет, что фрагменты ссылок на конечные точки `AcksTo`, `ReplyTo` и `Endpoint`, обозначающие универсальный код ресурса (URI), совпадают.  
  
-   R1103: ссылки на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.  
  
    -   В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предполагается, что параметры ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` совпадают, поэтому в подтверждениях и сообщениях встречной последовательности используются параметры ссылки на конечную точку `ReplyTo`.  
  
-   B1104: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создает необязательный элемент `Expires` или `Offer/Expires` в сообщении `CreateSequence`.  
  
-   B1105: при обращении к сообщению `CreateSequence` респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует значение `Expires` в элементе `CreateSequence` в качестве значения `Expires` в элементе `CreateSequenceResponse`. В противном случае респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] считывает и игнорирует значения `Expires` и `Offer/Expires`.  
  
-   B1106: при обращении к сообщению `CreateSequenceResponse` инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] считывает необязательное значение `Expires`, но не использует его.  
  
-   B1107: инициатор и респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создают необязательный элемент `IncompleteSequenceBehavior` в элементах `CreateSequence/Offer` и `CreateSequenceResponse`.  
  
-   B1108: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в элементе `DiscardFollowingFirstGap` используются только значения `NoDiscard` и `IncompleteSequenceBehavior`.  
  
    -   Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.  
  
-   B1109: если сообщение `CreateSequence` содержит элемент `Offer`, то односторонний респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отклоняет предложенную последовательность, отправляя в ответ сообщение `CreateSequenceResponse` без элемента `Accept`.  
  
-   B1110: если респондент отклоняет предложенную последовательность, инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] прерывает созданную последовательность.  
  
-   B1111: если сообщение `CreateSequence` не содержит элемент `Offer`, двусторонний респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отклоняет предложенную последовательность, отправляя в ответ ошибку `CreateSequenceRefused`.  
  
-   R1112: при установке с помощью механизма `Offer` двух встречных последовательностей, свойство `[address]` ссылки на конечную точку `CreateSequenceResponse/Accept/AcksTo` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.  
  
-   R1113: при установке с помощью механизма `Offer` двух встречных последовательностей, все сообщения от инициатора к респонденту в обеих последовательностях должны отправляться по одной и той же ссылке на конечную точку.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] протокол WS-ReliableMessaging используется для установки надежных сеансов между инициатором и респондентом. Реализация протокола WS-ReliableMessaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает создание надежного сеанса для односторонней связи, обмена запросами и ответами и для полностью двустороннего обмена сообщениями. Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями. Поскольку платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] гарантирует безопасность таких сеансов, включая сквозную защиту для обеспечения целостности сеанса, она позволяет проверять, что сообщения, предназначенные одной и той же стороне, достигнут одной и той же точки назначения. Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений. Таким образом, применяются ограничения R1102, R1112 и R1113 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для закрытия последовательности системы надежного обмена сообщениями по инициативе источника используются сообщения `CloseSequence` и `CloseSequenceResponse`. Точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не инициирует закрытие сеанса, а источник системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает закрытие последовательности, инициируемое точкой назначения. Действуют следующие ограничения.  
  
-   B1201: источник системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для закрытия последовательности всегда отправляет сообщение `CloseSequence`.  
  
-   B1202: источник системы надежного обмена сообщениями перед отправкой сообщения `CloseSequence` ждет подтверждения от всех сообщений последовательности.  
  
-   B1203: источник системы надежного обмена сообщениями всегда включает необязательный элемент `LastMsgNumber`, если в последовательности есть хотя бы одно сообщение.  
  
-   R1204: точка назначения системы надежного обмена сообщениями не должна инициировать закрытие последовательности путем отправки сообщения `CloseSequence`.  
  
-   B1205: после получения сообщения `CloseSequence` источник системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] полагает, что последовательность не завершена, и отправляет ошибку.  
  
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
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] после подтверждения `TerminateSequence/TerminateSequenceResponse` в первую очередь используется подтверждение `CloseSequence/CloseSequenceResponse`. Точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не инициирует завершение последовательности, а источник системы надежного обмена сообщениями не поддерживает завершение последовательности, инициируемое точкой назначения. Действуют следующие ограничения.  
  
-   B1301: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет сообщение `TerminateSequence` только после успешного подтверждения `CloseSequence/CloseSequenceResponse`.  
  
-   R1302: среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что элемент `LastMsgNumber` одинаков для всех сообщений `CloseSequence` и `TerminateSequence` в заданной последовательности. Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.  
  
-   B1303: при получении сообщения `TerminateSequence` после подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями отправляет в ответ сообщение `TerminateSequenceResponse`. Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.  
  
-   B1304: при получении сообщения `TerminateSequence` до подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет в ответ сообщение `TerminateSequenceResponse`. Если точка назначения системы надежного обмена сообщениями определяет, что в последовательности нет противоречий, она, прежде чем высвободить ресурсы, ждет в течение времени, заданного точкой назначения приложения, чтобы клиент мог получить последнее подтверждение. В противном случае точка назначения системы надежного обмена сообщениями сразу же высвобождает ресурсы и сообщает точке назначения приложения, что последовательность завершена, но не гарантированно, вызывая для этого событие `Faulted`.  
  
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
  
-   B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к возникновению ошибки и обращается к порядковые номера не выше, чем `xs:long`максимальное значение включительно, 9223372036854775807.  
  
 Пример заголовка `Sequence`.  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a>Запрос подтверждения  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в качестве механизма поддержки активности используется заголовок `AckRequested`.  
  
 Пример заголовка `AckRequested`.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для передачи подтверждений последовательностей протокола WS-ReliableMessaging используются сообщения приложений. Действуют следующие ограничения.  
  
-   R1601: При установке двух встречных последовательностей, устанавливаются с помощью `Offer` механизм, `SequenceAcknowledgement` заголовок может быть включено в любое сообщение приложения, передаваемых предполагаемому получателю. Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.  
  
-   B1602: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются заголовки `SequenceAcknowledgement`, содержащие элементы `Nack`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, содержит ли каждый элемент `Nack` номер последовательности, если нет, то элемент `Nack` и его значение пропускаются.  
  
 Пример заголовка `SequenceAcknowledgement`.  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a>Ошибки протокола WS-ReliableMessaging  
 Ниже приведен список ограничений, относящихся к реализации ошибок протокола WS-ReliableMessaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Действуют следующие ограничения.  
  
-   B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создает `MessageNumberRollover` ошибок.  
  
-   B1702: в SOAP 1.2, когда в конечной точке службы достигается максимальное число подключений и обработка новых подключений становится невозможной, среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает вложенный код ошибки `CreateSequenceRefused`, `netrm:ConnectionLimitReached`, как показано в следующем примере.  
  
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
 Поскольку протокол WS-ReliableMessaging использует протокол WS-Addressing, реализация WS-ReliableMessaging [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может создавать и передавать ошибки WS-Addressing. В этом разделе описаны ошибки WS-Addressing, которые среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]явным образом создает и передает на уровне WS-ReliableMessaging.  
  
-   B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает `Message Addressing Header Required` сбоя при выполнении одного из следующих действий:  
  
    -   в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;  
  
    -   в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;  
  
    -   в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.  
  
-   B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает `Endpoint Unavailable` ошибки для указания отсутствует конечная точка ожидает передачи данных, который может обрабатывать последовательности, основанной на изучение заголовки адресации в `CreateSequence` сообщения.  
  
## <a name="protocol-composition"></a>Сочетаемость протокола  
  
### <a name="composition-with-ws-addressing"></a>Сочетаемость с WS-Addressing  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации консорциума W3C по протоколу WS-Addressing версии 1.0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].  
  
 Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   R2101: с протоколом WS-ReliableMessaging можно использовать как версию WS-Addressing 2004/08, так и версию WS-Addressing 1.0.  
  
-   R2102: в рамках заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью механизма `Offer`, следует использовать только одну версию WS-Addressing.  
  
### <a name="composition-with-soap"></a>Сочетаемость с SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает использование с протоколом WS-Reliable Messaging как версии SOAP 1.1, так и версии SOAP 1.2.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Сочетаемость с WS-Security и WS-SecureConversation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает защиту последовательностей WS-ReliableMessaging с помощью безопасного транспорта (HTTPS) и совместимости с протоколами WS-Security и WS-Secure Conversation. Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   R2301: в дополнение к обеспечению целостности и конфиденциальности отдельных сообщений для защиты целостности последовательности WS-ReliableMessaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требуется использовать протокол WS-Secure.  
  
-   R2302:AWS-Secure Conversation должен быть установлен до установки последовательностях WS-ReliableMessaging.  
  
-   R2303: если время существования последовательности WS-ReliableMessaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.  
  
-   B2304:ws-последовательности ReliableMessaging или пары коррелированные встречные последовательности всегда привязан к одного сеанса WS-SecureConversation.  
  
-   R2305: при использовании с протоколом WS-Secure Conversation респонденту [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] необходимо, чтобы сообщение `CreateSequence` содержало элемент `wsse:SecurityTokenReference` и заголовок `wsrm:UsesSequenceSTR`.  
  
 Пример заголовка `UsesSequenceSTR`.  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a>Сочетаемость с сеансами SSL/TLS  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает совместное использование с сеансами SSL/TLS.  
  
-   B2401: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются заголовки `wsrm:UsesSequenceSSL`.  
  
-   R2402: инициатор системы надежного обмена сообщениями не должен отправлять сообщение `CreateSequence` с заголовком `wsrm:UsesSequenceSSL` респонденту [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### <a name="composition-with-ws-policy"></a>Сочетаемость с WS-Policy  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает две версии протокола WS-Policy: WS-Policy 1.2 и WS-Policy 1.5.  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a>Утверждение WS-ReliableMessaging WS-Policy  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] утверждение WS-ReliableMessaging WS-Policy `wsrm:RMAssertion` используется для описания возможностей конечных точек. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B3001: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] к элементам `wsrmn:RMAssertion` прикрепляется проверочное утверждение WS-Policy `wsdl:binding`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает вложения в элементы `wsdl:binding` и `wsdl:port`.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] никогда не создает тег `wsp:Optional`.  
  
-   B3003: при обращении к утверждению WS-Policy `wsrmp:RMAssertion` [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] игнорирует тег `wsp:Optional` и трактует политику WS-RM Policy как обязательную.  
  
-   R3004: поскольку [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не может использоваться совместно с сеансами SSL/TLS, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не принимает политики, задающие `wsrmp:SequenceTransportSecurity`.  
  
-   B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создает элемент `wsrmp:DeliveryAssurance`.  
  
-   B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда задает гарантию доставки `wsrmp:ExactlyOnce`.  
  
-   B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и считывает следующие свойства утверждения WS-ReliableMessaging и реализует управление над ними через элемент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`.  
  
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
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует расширяемость WS-ReliableMessaging, чтобы обеспечить более строгое управление над потоком последовательности сообщений.  
  
 Включить управление потоком, задав `ReliableSessionBindingElement` `FlowControlEnabled``boolean` свойства `true`. Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   B4001: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `netrm:BufferRemaining`, используя возможности расширения элемента заголовка `SequenceAcknowledgement`, как показано в следующем примере.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: даже если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требует наличия в заголовке `netrm:BufferRemaining` элемента `SequenceAcknowledgement`.  
  
-   B4003: точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует элемент `netrm:BufferRemaining`, чтобы задать число новых сообщений, которые она может поместить в буфер.  
  
-   Включен B4004:When надежного обмена сообщениями потока управления, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Источник надежного обмена сообщениями использует значение `netrm:BufferRemaining` регулирования передачу сообщений.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает целые значения элемента `netrm:BufferRemaining` в интервале от 0 до 4096 включительно и считывает целые значения в интервале от 0 до максимального значения типа `xs:int` (`maxInclusive`, 214748364) включительно.  
  
## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями  
 В этом разделе описана работа среды [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании протокола WS-ReliableMessaging для различных шаблонов обмена сообщениями. Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:  
  
-   неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;  
  
-   адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.  
  
### <a name="one-way-non-addressable-initiator"></a>Односторонний неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` без элемента `Offer` в HTTP-запросе и ожидает сообщения `CreateSequenceResponse` в HTTP-ответе. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в HTTP-ответе.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает подтверждения при ответе на все сообщения, кроме сообщения `CreateSequence` и сообщений об ошибках. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда передает отдельное подтверждение в HTTP-ответе для всех сообщений последовательности и сообщений `AckRequested`.  
  
#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CloseSequence` в HTTP-запросе и ожидает сообщения `CreateSequenceResponse` в HTTP-ответе. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CloseSequenceResponse` в HTTP-ответе.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequence` в HTTP-запросе и ожидает сообщения `TerminateSequenceResponse` в HTTP-ответе. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequenceResponse` в HTTP-ответе.  
  
### <a name="one-way-addressable-initiator"></a>Односторонний адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и один исходящий канал HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP-запросы. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` без элемента `Offer` в HTTP-запросе. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в HTTP-запросе.  
  
### <a name="duplex-addressable-initiator"></a>Дуплексный адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон полностью асинхронного двустороннего обмена сообщениями с использованием двух последовательностей через один входящий и один исходящий канал HTTP. Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP-запросы. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` с элементом `Offer` в HTTP-запросе. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что сообщение `CreateSequence` содержит элемент `Offer`, после чего создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept`.  
  
#### <a name="sequence-lifetime"></a>Время существования последовательности  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] две последовательности рассматриваются в качестве одного полностью двустороннего сеанса.  
  
 После разрыва одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает, что удаленная точка доступа вызовет разрыв в обеих последовательностях. После чтения разрыва в одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вызывает разрывы в обеих последовательностях.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности. И наоборот, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон одностороннего обмена сообщениями «запрос-ответ» с использованием двух последовательностей через один канал HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` с элементом `Offer` в HTTP-запросе и ожидает сообщения `CreateSequenceResponse` в HTTP-ответе. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept` в HTTP-ответе.  
  
#### <a name="one-way-message"></a>Односторонний обмен сообщениями  
 Для одностороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает отдельное сообщение `SequenceAcknowledgement` в HTTP-ответе. Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
#### <a name="two-way-messages"></a>Двусторонний обмен сообщениями  
 Для реализации протокола двустороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает сообщение последовательности ответов в HTTP-ответе. Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.  
  
 Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.  
  
#### <a name="retrying-replies"></a>Повторные попытки ответов  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для обеспечения корреляции между сообщениями протокола двустороннего обмена сообщениями используется корреляция между HTTP-запросами и ответами. Поэтому инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не прекращает попытки отправки сообщения последовательности запросов в случае подтверждения этого сообщения, а дожидается HTTP-ответа, содержащего элемент `SequenceAcknowledgement`, ответ приложения или ошибку. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] повторяет в HTTP-ответе ответы на запрос, с которым связан этот ответ.  
  
#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence  
 После получения всех сообщений последовательности ответов и подтверждений для всех сообщений односторонней последовательности запросов инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в HTTP-запросе передает сообщение `CloseSequence` для данной последовательности запросов и ожидает сообщения `CloseSequenceResponse` в HTTP-ответе.  
  
 Закрытие последовательности запросов неявным образом закрывает последовательность ответов. Это значит, что инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] включает последнее подтверждение `SequenceAcknowledgement` последовательности ответов в сообщение `CloseSequence`, а в последовательности ответов нет ответного сообщения `CloseSequence`.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет все ответы и подтверждения и в HTTP-ответе передает сообщение `CloseSequenceResponse`.  
  
#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence  
 После получения сообщения `CloseSequenceResponse` инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequence` для последовательности запросов в HTTP-запросе и ожидает сообщения `TerminateSequenceResponse` в HTTP-ответе.  
  
 Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов. Это значит, что инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] включает последнее подтверждение `SequenceAcknowledgement` последовательности ответов в сообщение `TerminateSequence`, и что в последовательности ответов нет ответного сообщения `TerminateSequence`.  
  
 Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequenceResponse` в HTTP-ответе.  
  
### <a name="requestreply-addressable-initiator"></a>Обмен сообщениями запрос-ответ, адресуемый инициатор  
  
#### <a name="binding"></a>Привязка  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает шаблон обмена сообщениями запрос-ответ с использованием двух последовательностей через один входящий и один исходящий канал HTTP. Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует для передачи всех сообщений HTTP-запросы. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.  
  
#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence  
 Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` с элементом `Offer` в HTTP-запросе. Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что сообщение `CreateSequence` содержит элемент `Offer`, после чего создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept`.  
  
#### <a name="requestreply-correlation"></a>Корреляция запросов и ответов  
 Следующие действия относятся ко всем связанным запросам и ответам.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что все сообщения с запросами приложения содержат ссылку на конечную точку `ReplyTo` и значение `MessageId`.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] применяет ссылку на локальную конечную точку в качестве значения `ReplyTo` каждого сообщения с запросом приложения. Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что все сообщения входящих запросов содержат значения `MessageId` и `ReplyTo`.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что значения универсальных кодов ресурсов (URI) в ссылке на конечную точку `ReplyTo` всех сообщений запросов приложения совпадают с определенной выше ссылкой на локальную конечную точку.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что все ответы содержат правильные заголовки `RelatesTo` и `To`, соответствующие правилам связывания запросов и ответов `wsa`.
