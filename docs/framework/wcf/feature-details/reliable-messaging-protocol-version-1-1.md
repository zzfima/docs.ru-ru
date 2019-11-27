---
title: Протокол надежного обмена сообщениями, версия 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 9320787317131f42c4a82c6114a16fdea87567f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283309"
---
# <a name="reliable-messaging-protocol-version-11"></a>Протокол надежного обмена сообщениями, версия 1,1

В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для протокола WS-ReliableMessaging Февраль 2007 (версия 1,1), необходимого для взаимодействия с использованием транспорта HTTP. WCF использует спецификацию WS-ReliableMessaging с ограничениями и пояснениями, описанными в этом разделе. Обратите внимание, что протокол WS-ReliableMessaging версии 1,1 реализуется начиная с .NET Framework 3,5.

Протокол WS-ReliableMessaging Февраль 2007 реализован в WCF с помощью <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.

Для удобства объяснения в этом разделе используются следующие роли:

- инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;

- респондент: служба, получающая запросы инициатора.

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

WCF реализует `CreateSequence` и `CreateSequenceResponse` сообщения для создания надежной последовательности обмена сообщениями. Действуют следующие ограничения.

- B1101: инициатор WCF использует ту же ссылку на конечную точку, что и `ReplyTo`сообщения `CreateSequence`, `AcksTo` и `Offer/Endpoint`.

- R1102: адреса ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь идентичные строковые представления, чтобы они совпадали на уровне октетов.

  - После создания последовательности в WCF-ответчике проверяется, что URI-часть `AcksTo`, `ReplyTo` и `Endpoint` ссылок на конечные точки идентичны.

- R1103: ссылки на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.

  - WCF не применяет принудительно, но предполагает, что ссылочные параметры `AcksTo`, `ReplyTo` и `Offer/Endpoint` ссылок на конечные точки в `CreateSequence` идентичны и используют ссылочные параметры из ссылки на конечную точку `ReplyTo` для подтверждения и последовательного обмена сообщениями.

- B1104: инициатор WCF не создает необязательный элемент `Expires` или `Offer/Expires` в сообщении `CreateSequence`.

- B1105. при доступе к сообщению `CreateSequence` WCF ответчик использует значение `Expires` в элементе `CreateSequence` в качестве значения `Expires` в элементе `CreateSequenceResponse`. В противном случае WCF ответчик считывает и игнорирует значения `Expires` и `Offer/Expires`.

- B1106: при доступе к сообщению `CreateSequenceResponse` инициатор WCF считывает необязательное значение `Expires`, но не использует его.

- B1107. Инициатор и ответчик WCF всегда создают необязательный элемент `IncompleteSequenceBehavior` в элементах `CreateSequence/Offer` и `CreateSequenceResponse`.

- B1108: WCF использует только значения `DiscardFollowingFirstGap` и `NoDiscard` в элементе `IncompleteSequenceBehavior`.

  - Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.

- B1109: Если `CreateSequence` содержит элемент `Offer`, то один из способов, который WCF-ответчик отклоняет предлагаемую последовательность, отвечая на `CreateSequenceResponse` без элемента `Accept`.

- B1110: Если отвечающий надежный ответчик отклоняет предлагаемую последовательность, инициатор WCF завершается ошибкой вновь установленной последовательности.

- B1111: Если `CreateSequence` не содержит элемент `Offer`, двусторонний ответчик WCF отклоняет предлагаемую последовательность, отвечая на ошибку `CreateSequenceRefused`.

- R1112: при установке с помощью механизма `Offer` двух встречных последовательностей, свойство `[address]` ссылки на конечную точку `CreateSequenceResponse/Accept/AcksTo` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.

- R1113: при установке с помощью механизма `Offer` двух встречных последовательностей, все сообщения от инициатора к респонденту в обеих последовательностях должны отправляться по одной и той же ссылке на конечную точку.

WCF использует WS-ReliableMessaging для установления надежных сеансов между инициатором и респондентом. Реализация WCF WS-ReliableMessaging обеспечивает надежный сеанс для односторонних, однонаправленных и полноценных шаблонов обмена сообщениями. Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями. Поскольку WCF предоставляет гарантию безопасности для такого сеанса, включая сквозную защиту для целостности сеанса, целесообразно убедиться, что сообщения, предназначенные для одной и той же стороны, приходят на одно и то же место назначения. Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений. Таким образом, ограничения R1102, r1112 и R1113 применяются к WCF.

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

WCF использует `CloseSequence` и `CloseSequenceResponse` сообщения для надежного завершения работы системы обмена сообщениями. Назначение надежного обмена сообщениями WCF не инициирует завершение работы, и Источник надежного обмена сообщениями WCF не поддерживает завершение работы, инициированное адресатом надежного обмена сообщениями. Действуют следующие ограничения.

- B1201: Источник надежного обмена сообщениями WCF всегда отправляет `CloseSequence` сообщение, чтобы завершить работу последовательности.

- B1202: источник системы надежного обмена сообщениями перед отправкой сообщения `CloseSequence` ждет подтверждения от всех сообщений последовательности.

- B1203: источник системы надежного обмена сообщениями всегда включает необязательный элемент `LastMsgNumber`, если в последовательности есть хотя бы одно сообщение.

- R1204: точка назначения системы надежного обмена сообщениями не должна инициировать закрытие последовательности путем отправки сообщения `CloseSequence`.

- B1205. После получения сообщения `CloseSequence` Источник надежного обмена сообщениями WCF считает последовательность незавершенной и отправляет ошибку.

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
```

Пример сообщения `CloseSequenceResponse`:

```xml
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

WCF в основном использует `TerminateSequence/TerminateSequenceResponse`ное подтверждение связи после завершения `CloseSequence/CloseSequenceResponse` подтверждения. Назначение надежного обмена сообщениями WCF не инициирует завершение и Источник надежного обмена сообщениями не поддерживает прерывание, инициированное адресатом. Действуют следующие ограничения.

- B1301: инициатор WCF отправляет сообщение `TerminateSequence` только после успешного завершения подтверждения `CloseSequence/CloseSequenceResponse`.

- R1302: WCF проверяет, что элемент `LastMsgNumber` согласован по всем `CloseSequence` и `TerminateSequence` сообщениям для данной последовательности. Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.

- B1303: при получении сообщения `TerminateSequence` после подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями отправляет в ответ сообщение `TerminateSequenceResponse`. Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.

- B1304: при получении сообщения `TerminateSequence` до `CloseSequence/CloseSequenceResponse` подтверждения, назначение надежного обмена сообщениями WCF реагирует на `TerminateSequenceResponse` сообщение. Если точка назначения системы надежного обмена сообщениями определяет, что в последовательности нет противоречий, она, прежде чем высвободить ресурсы, ждет в течение времени, заданного точкой назначения приложения, чтобы клиент мог получить последнее подтверждение. В противном случае точка назначения системы надежного обмена сообщениями сразу же высвобождает ресурсы и сообщает точке назначения приложения, что последовательность завершена, но не гарантированно, вызывая для этого событие `Faulted`.

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
```

Пример сообщения `TerminateSequenceResponse`:

```xml
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

- B1401: WCF создает и обращается к порядковым номерам не выше максимального значения `xs:long`, 9223372036854775807.

Пример заголовка `Sequence`.

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a>Запрос подтверждения

WCF использует заголовок `AckRequested` в качестве механизма поддержания активности.

Пример заголовка `AckRequested`.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

WCF использует механизм свинка для подтверждения последовательностей, предоставляемых WS-надежный обмен сообщениями. Действуют следующие ограничения.

- R1601: Если две обратные последовательности установлены с помощью механизма `Offer`, заголовок `SequenceAcknowledgement` может быть добавлен в любое сообщение приложения, передаваемое предполагаемому получателю. Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.

- B1602: WCF не создает `SequenceAcknowledgement` заголовков, содержащих элементы `Nack`. WCF проверяет, что каждый элемент `Nack` содержит порядковый номер, но в противном случае не учитывает `Nack` элемент и значение.

 Пример заголовка `SequenceAcknowledgement`.

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a>Ошибки протокола WS-ReliableMessaging

Ниже приведен список ограничений, которые применяются к реализации WCF ошибок WS-ReliableMessaging. Действуют следующие ограничения.

- B1701: WCF не создает `MessageNumberRollover` ошибок.

- B1702: по протоколу SOAP 1,2, когда конечная точка службы достигает предельного числа подключений и не может обработать новые соединения, WCF создает вложенный `CreateSequenceRefused` неисправного кода, `netrm:ConnectionLimitReached`, как показано в следующем примере.

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

Поскольку WS-ReliableMessaging использует WS-Addressing, реализация WCF WS-ReliableMessaging может создавать и передавать ошибки WS-Addressing. В этом разделе рассматриваются ошибки WS-Addressing, которые WCF явно создает и передает на уровне WS-ReliableMessaging:

- B1801: WCF создает и передает ошибку `Message Addressing Header Required`, если выполняется одно из следующих условий.

  - в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;

  - в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;

  - в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.

- B1802: WCF создает и передает ошибку `Endpoint Unavailable`, чтобы указать, что не существует прослушивания конечных точек, которое может обработать последовательность на основе проверки заголовков адресации в сообщении `CreateSequence`.

## <a name="protocol-composition"></a>Сочетаемость протокола

### <a name="composition-with-ws-addressing"></a>Сочетаемость с WS-Addressing

WCF поддерживает две версии WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации консорциума W3C WS-Addressing 1,0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].

Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing. Ниже приведен список ограничений, применяемых к WCF.

- R2101: с протоколом WS-ReliableMessaging можно использовать как версию WS-Addressing 2004/08, так и версию WS-Addressing 1.0.

- R2102: в рамках заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью механизма `Offer`, следует использовать только одну версию WS-Addressing.

### <a name="composition-with-soap"></a>Сочетаемость с SOAP

WCF поддерживает использование SOAP 1,1 и SOAP 1,2 с WS-надежный обмен сообщениями.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Сочетаемость с WS-Security и WS-SecureConversation

WCF обеспечивает защиту для последовательностей WS-ReliableMessaging с помощью защищенного транспорта (HTTPS), композиции с WS-Security и компоновки с WS-Secure Conversation. Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно. Ниже приведен список ограничений, применяемых к WCF.

- R2301. чтобы защитить целостность последовательности WS-ReliableMessaging в дополнение к целостности и конфиденциальности отдельных сообщений, WCF требует, чтобы использовался протокол WS-Secure Conversation.

- R2302:перед установкой последовательностей WS-ReliableMessagingдолжен быть установлен сеанс WS-Secure Conversation.

- R2303: если время существования последовательности WS-ReliableMessaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.

- B2304:последовательность WS-ReliableMessaging или пара встречных последовательностей всегда связаны с одним сеансом WS-SecureConversation.

- R2305. при сопоставлении с WS-Secure conversations для WCF требуется, чтобы `CreateSequence` сообщение содержало элемент `wsse:SecurityTokenReference` и заголовок `wsrm:UsesSequenceSTR`.

 Пример заголовка `UsesSequenceSTR`.

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a>Сочетаемость с сеансами SSL/TLS

WCF не поддерживает композицию для сеансов SSL/TLS:

- B2401: WCF не создает заголовок `wsrm:UsesSequenceSSL`.

- R2402: инициатор надежного обмена сообщениями не должен передавать сообщение `CreateSequence` с заголовком `wsrm:UsesSequenceSSL` в ответчик WCF.

### <a name="composition-with-ws-policy"></a>Сочетаемость с WS-Policy

WCF поддерживает две версии WS-Policy: WS-Policy 1,2 и WS-Policy 1,5.

## <a name="ws-reliablemessaging-ws-policy-assertion"></a>Утверждение WS-ReliableMessaging WS-Policy

Для описания возможностей конечных точек WCF использует утверждение WS-ReliableMessaging WS-Policy `wsrm:RMAssertion`. Ниже приведен список ограничений, применяемых к WCF.

- B3001: WCF присоединяет `wsrmn:RMAssertion` утверждения WS-Policy к `wsdl:binding`ным элементам. WCF поддерживает оба вложения для `wsdl:binding` и `wsdl:port` элементов.

- B3002: WCF никогда не создает тег `wsp:Optional`.

- B3003. при доступе к утверждению `wsrmp:RMAssertion` WS-Policy WCF игнорирует тег `wsp:Optional` и обрабатывает политику WS-RM как обязательную.

- R3004: поскольку WCF не сопоставлена с сеансами SSL/TLS, WCF не принимает политику, задающую `wsrmp:SequenceTransportSecurity`.

- B3005: WCF всегда создает элемент `wsrmp:DeliveryAssurance`.

- B3006. в WCF всегда указывается гарантия доставки `wsrmp:ExactlyOnce`.

- B3007: WCF создает и считывает следующие свойства утверждения WS-ReliableMessaging и обеспечивает контроль над ними в`ReliableSessionBindingElement`WCF:

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

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

WCF использует расширяемость WS-ReliableMessaging для предоставления дополнительного более строгого контроля над потоком сообщений последовательности.

Управление потоком включается путем присвоения свойству <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> значения `true`. Ниже приведен список ограничений, применяемых к WCF.

- B4001. при включении управления потоком надежного обмена сообщениями WCF создает элемент `netrm:BufferRemaining` в расширяемости элемента заголовка `SequenceAcknowledgement`, как показано в следующем примере.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- B4002. даже если включен механизм надежного управления потоком сообщений, WCF не требует элемент `netrm:BufferRemaining` в заголовке `SequenceAcknowledgement`.

- B4003: в назначении надежного обмена сообщениями WCF используется `netrm:BufferRemaining`, чтобы указать, сколько новых сообщений может быть помещено в буфер.

- B4004. при включении управления потоком надежного обмена сообщениями Источник надежного обмена сообщениями WCF использует значение `netrm:BufferRemaining` для регулирования передачи сообщений.

- B4005: WCF создает `netrm:BufferRemaining` целочисленных значений от 0 до 4096 включительно и считывает целочисленные значения от 0 до `xs:int``maxInclusive` значение 214748364 включительно.

## <a name="message-exchange-patterns"></a>Шаблоны обмена сообщениями

В этом разделе описывается поведение WCF при использовании WS-ReliableMessaging для различных шаблонов обмена сообщениями. Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:

- неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;

- адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.

### <a name="one-way-non-addressable-initiator"></a>Односторонний неадресуемый инициатор

#### <a name="binding"></a>Привязка

WCF предоставляет односторонний шаблон обмена сообщениями, используя одну последовательность по одному каналу HTTP. WCF использует HTTP-запросы для передачи всех сообщений от инициатора в ответчик и HTTP-ответы для передачи всех сообщений от респондента инициатору.

#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence

Инициатор WCF передает `CreateSequence` сообщение без элемента `Offer` в HTTP-запросе и ждет сообщения `CreateSequenceResponse` в HTTP-ответе. WCF-ответчик создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в ответе HTTP.

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

Инициатор WCF обрабатывает подтверждения по ответу всех сообщений, за исключением `CreateSequence` сообщения и сообщений об ошибках. WCF-ответчик всегда передает изолированное подтверждение ответа HTTP всем последовательностью и `AckRequested` сообщениям.

#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence

Инициатор WCF передает `CloseSequence` сообщение в HTTP-запросе и ждет сообщения `CreateSequenceResponse` в HTTP-ответе. WCF-ответчик передает `CloseSequenceResponse` сообщение в ответе HTTP.

#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence

Инициатор WCF передает `TerminateSequence` сообщение в HTTP-запросе и ждет сообщения `TerminateSequenceResponse` в HTTP-ответе. WCF-ответчик передает `TerminateSequenceResponse` сообщение в ответе HTTP.

### <a name="one-way-addressable-initiator"></a>Односторонний адресуемый инициатор

#### <a name="binding"></a>Привязка

WCF предоставляет односторонний шаблон обмена сообщениями, используя одну последовательность для одного входящего и одного исходящего HTTP-канала. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.

#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence

Инициатор WCF передает `CreateSequence` сообщение без элемента `Offer` в HTTP-запросе. WCF-ответчик создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в запросе HTTP.

### <a name="duplex-addressable-initiator"></a>Дуплексный адресуемый инициатор

#### <a name="binding"></a>Привязка

WCF предоставляет полностью асинхронный, двусторонний шаблон обмена сообщениями с использованием двух последовательностей по одному входящему и одному исходящему каналу HTTP. Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.

#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence

Инициатор WCF передает `CreateSequence` сообщение с элементом `Offer` в HTTP-запросе. WCF-ответчик гарантирует, что `CreateSequence` имеет элемент `Offer`, затем создает последовательность и передает `CreateSequenceResponse` сообщение с помощью элемента `Accept`.

#### <a name="sequence-lifetime"></a>Время существования последовательности

WCF рассматривает две последовательности как один полностью дуплексный сеанс.

При создании ошибки, которая не выполняет одну последовательность, WCF ждет, что удаленная конечная точка будет выполнять обе последовательности. При чтении ошибки, которая не выполняет одну последовательность, WCF завершает обе последовательности.

WCF может закрыть свою исходящую последовательность и продолжить обработку сообщений на его входящей последовательности. И наоборот, WCF может обработать закрытие входящей последовательности и продолжить отправку сообщений по исходящей последовательности.

### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор

#### <a name="binding"></a>Привязка

WCF предоставляет односторонний шаблон обмена сообщениями типа «запрос-ответ» с использованием двух последовательностей по одному каналу HTTP. WCF использует HTTP-запросы для передачи всех сообщений от инициатора в ответчик и HTTP-ответы для передачи всех сообщений от респондента инициатору.

#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence

Инициатор WCF передает `CreateSequence` сообщение с элементом `Offer` в HTTP-запросе и ждет сообщения `CreateSequenceResponse` в HTTP-ответе. WCF-ответчик создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept` в ответе HTTP.

#### <a name="one-way-message"></a>Односторонний обмен сообщениями

Чтобы успешно завершить односторонний обмен сообщениями, инициатор WCF передает сообщение последовательности запроса по HTTP-запросу и получает автономное сообщение `SequenceAcknowledgement` в ответе HTTP. Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.

Ответчик WCF может ответить на запрос с помощью подтверждения, ошибки или ответа с пустым телом и кодом состояния HTTP 202.

#### <a name="two-way-messages"></a>Двусторонний обмен сообщениями

Для успешного завершения двустороннего обмена сообщениями инициатор WCF передает сообщение последовательности запросов по HTTP-запросу и получает сообщение последовательности ответов в ответе HTTP. Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.

Ответчик WCF может ответить на запрос с ответом на приложение, ошибку или ответ с пустым телом и кодом состояния HTTP 202.

Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.

#### <a name="retrying-replies"></a>Повторные попытки ответов

WCF использует корреляцию HTTP-ответа "запрос — ответ" для двусторонней корреляции протокола обмена сообщениями. По этой причине инициатор WCF не прекращает повторную попытку сообщения последовательности запроса, когда сообщение последовательностей запроса подтверждено, а когда HTTP-ответ содержит `SequenceAcknowledgement`, ответ приложения или ошибку. WCF-ответчик повторяет ответы в ответе HTTP запроса, к которому коррелирован ответ.

#### <a name="closesequence-exchange"></a>Обмен сообщениями CloseSequence

После получения всех сообщений последовательности ответов и подтверждений для всех однонаправленных сообщений последовательности запросов инициатор WCF передает `CloseSequence` сообщение для последовательности запросов по HTTP-запросу и ожидает `CloseSequenceResponse` в HTTP-ответе.

Закрытие последовательности запросов неявным образом закрывает последовательность ответов. Это означает, что инициатор WCF включает окончательный `SequenceAcknowledgement` в `CloseSequence` сообщении, а последовательность ответов не имеет `CloseSequence` Exchange.

WCF-ответчик гарантирует, что все ответы будут подтверждены, и передает `CloseSequenceResponse` сообщение в ответе HTTP.

#### <a name="terminatesequence-exchange"></a>Обмен сообщениями TerminateSequence

После получения сообщения `CloseSequenceResponse` инициатор WCF передает `TerminateSequence` сообщение для последовательности запроса по HTTP-запросу и ожидает `TerminateSequenceResponse` в HTTP-ответе.

Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов. Это означает, что инициатор WCF включает окончательный `SequenceAcknowledgement` в `TerminateSequence` сообщении, а последовательность ответов не имеет `TerminateSequence` Exchange.

WCF-ответчик передает `TerminateSequenceResponse` сообщение в ответе HTTP.

### <a name="requestreply-addressable-initiator"></a>Обмен сообщениями запрос-ответ, адресуемый инициатор

#### <a name="binding"></a>Привязка

WCF предоставляет шаблон обмена сообщениями типа «запрос-ответ» с использованием двух последовательностей по одному входящему и одному исходящему HTTP-каналу. Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`. WCF использует HTTP-запросы для передачи всех сообщений. Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.

#### <a name="createsequence-exchange"></a>Обмен сообщениями CreateSequence

Инициатор WCF передает `CreateSequence` сообщение с элементом `Offer` в HTTP-запросе. WCF-ответчик гарантирует, что `CreateSequence` имеет `Offer` элемент, затем создает последовательность и передает `CreateSequenceResponse` сообщение с элементом `Accept`.

#### <a name="requestreply-correlation"></a>Корреляция запросов и ответов

Следующие действия относятся ко всем связанным запросам и ответам.

- WCF гарантирует, что все сообщения запроса приложения по`ReplyTo` ссылку на конечную точку и `MessageId`.

- WCF применяет ссылку на локальную конечную точку в качестве `ReplyTo`сообщения запроса приложения. Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.

- WCF гарантирует, что входящие сообщения запроса поставили `MessageId` и `ReplyTo`.

- WCF гарантирует, что URI ссылки на конечную точку `ReplyTo` всех сообщений запроса приложения соответствует ссылке на локальную конечную точку, как определено ранее.

- WCF гарантирует, что все ответы представили правильные `RelatesTo` и `To` заголовки, следующие `wsa` правил корреляции "запрос-ответ".
