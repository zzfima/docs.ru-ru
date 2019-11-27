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
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="c0b7e-102">Протокол надежного обмена сообщениями, версия 1,1</span><span class="sxs-lookup"><span data-stu-id="c0b7e-102">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="c0b7e-103">В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для протокола WS-ReliableMessaging Февраль 2007 (версия 1,1), необходимого для взаимодействия с использованием транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="c0b7e-104">WCF использует спецификацию WS-ReliableMessaging с ограничениями и пояснениями, описанными в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="c0b7e-105">Обратите внимание, что протокол WS-ReliableMessaging версии 1,1 реализуется начиная с .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with .NET Framework 3.5.</span></span>

<span data-ttu-id="c0b7e-106">Протокол WS-ReliableMessaging Февраль 2007 реализован в WCF с помощью <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="c0b7e-107">Для удобства объяснения в этом разделе используются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="c0b7e-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="c0b7e-108">инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;</span><span class="sxs-lookup"><span data-stu-id="c0b7e-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="c0b7e-109">респондент: служба, получающая запросы инициатора.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-109">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="c0b7e-110">В этом документе используются префиксы и пространства имен, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="c0b7e-111">Префикс</span><span class="sxs-lookup"><span data-stu-id="c0b7e-111">Prefix</span></span>|<span data-ttu-id="c0b7e-112">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c0b7e-112">Namespace</span></span>|
|-|-|
|<span data-ttu-id="c0b7e-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="c0b7e-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|<span data-ttu-id="c0b7e-114">netrm</span><span class="sxs-lookup"><span data-stu-id="c0b7e-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|
|<span data-ttu-id="c0b7e-115">s</span><span class="sxs-lookup"><span data-stu-id="c0b7e-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|
|<span data-ttu-id="c0b7e-116">wsa</span><span class="sxs-lookup"><span data-stu-id="c0b7e-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="c0b7e-117">wsse</span><span class="sxs-lookup"><span data-stu-id="c0b7e-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|<span data-ttu-id="c0b7e-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="c0b7e-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|<span data-ttu-id="c0b7e-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="c0b7e-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|<span data-ttu-id="c0b7e-120">wsp</span><span class="sxs-lookup"><span data-stu-id="c0b7e-120">wsp</span></span>|<span data-ttu-id="c0b7e-121">(WS-Policy 1.2 или WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="c0b7e-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="c0b7e-122">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="c0b7e-122">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="c0b7e-123">Создание последовательности</span><span class="sxs-lookup"><span data-stu-id="c0b7e-123">Sequence Creation</span></span>

<span data-ttu-id="c0b7e-124">WCF реализует `CreateSequence` и `CreateSequenceResponse` сообщения для создания надежной последовательности обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="c0b7e-125">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-125">The following constraints apply:</span></span>

- <span data-ttu-id="c0b7e-126">B1101: инициатор WCF использует ту же ссылку на конечную точку, что и `ReplyTo`сообщения `CreateSequence`, `AcksTo` и `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="c0b7e-127">R1102: адреса ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь идентичные строковые представления, чтобы они совпадали на уровне октетов.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="c0b7e-128">После создания последовательности в WCF-ответчике проверяется, что URI-часть `AcksTo`, `ReplyTo` и `Endpoint` ссылок на конечные точки идентичны.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="c0b7e-129">R1103: ссылки на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="c0b7e-130">WCF не применяет принудительно, но предполагает, что ссылочные параметры `AcksTo`, `ReplyTo` и `Offer/Endpoint` ссылок на конечные точки в `CreateSequence` идентичны и используют ссылочные параметры из ссылки на конечную точку `ReplyTo` для подтверждения и последовательного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="c0b7e-131">B1104: инициатор WCF не создает необязательный элемент `Expires` или `Offer/Expires` в сообщении `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="c0b7e-132">B1105. при доступе к сообщению `CreateSequence` WCF ответчик использует значение `Expires` в элементе `CreateSequence` в качестве значения `Expires` в элементе `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="c0b7e-133">В противном случае WCF ответчик считывает и игнорирует значения `Expires` и `Offer/Expires`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="c0b7e-134">B1106: при доступе к сообщению `CreateSequenceResponse` инициатор WCF считывает необязательное значение `Expires`, но не использует его.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="c0b7e-135">B1107. Инициатор и ответчик WCF всегда создают необязательный элемент `IncompleteSequenceBehavior` в элементах `CreateSequence/Offer` и `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="c0b7e-136">B1108: WCF использует только значения `DiscardFollowingFirstGap` и `NoDiscard` в элементе `IncompleteSequenceBehavior`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="c0b7e-137">Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="c0b7e-138">B1109: Если `CreateSequence` содержит элемент `Offer`, то один из способов, который WCF-ответчик отклоняет предлагаемую последовательность, отвечая на `CreateSequenceResponse` без элемента `Accept`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="c0b7e-139">B1110: Если отвечающий надежный ответчик отклоняет предлагаемую последовательность, инициатор WCF завершается ошибкой вновь установленной последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="c0b7e-140">B1111: Если `CreateSequence` не содержит элемент `Offer`, двусторонний ответчик WCF отклоняет предлагаемую последовательность, отвечая на ошибку `CreateSequenceRefused`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="c0b7e-141">R1112: при установке с помощью механизма `Offer` двух встречных последовательностей, свойство `[address]` ссылки на конечную точку `CreateSequenceResponse/Accept/AcksTo` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="c0b7e-142">R1113: при установке с помощью механизма `Offer` двух встречных последовательностей, все сообщения от инициатора к респонденту в обеих последовательностях должны отправляться по одной и той же ссылке на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="c0b7e-143">WCF использует WS-ReliableMessaging для установления надежных сеансов между инициатором и респондентом.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="c0b7e-144">Реализация WCF WS-ReliableMessaging обеспечивает надежный сеанс для односторонних, однонаправленных и полноценных шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="c0b7e-145">Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="c0b7e-146">Поскольку WCF предоставляет гарантию безопасности для такого сеанса, включая сквозную защиту для целостности сеанса, целесообразно убедиться, что сообщения, предназначенные для одной и той же стороны, приходят на одно и то же место назначения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="c0b7e-147">Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="c0b7e-148">Таким образом, ограничения R1102, r1112 и R1113 применяются к WCF.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="c0b7e-149">Пример сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-149">An example of a `CreateSequence` message.</span></span>

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

<span data-ttu-id="c0b7e-150">Пример сообщения `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-150">An example of a `CreateSequenceResponse` message.</span></span>

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

### <a name="closing-a-sequence"></a><span data-ttu-id="c0b7e-151">Закрытие последовательности</span><span class="sxs-lookup"><span data-stu-id="c0b7e-151">Closing a Sequence</span></span>

<span data-ttu-id="c0b7e-152">WCF использует `CloseSequence` и `CloseSequenceResponse` сообщения для надежного завершения работы системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="c0b7e-153">Назначение надежного обмена сообщениями WCF не инициирует завершение работы, и Источник надежного обмена сообщениями WCF не поддерживает завершение работы, инициированное адресатом надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="c0b7e-154">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-154">The following constraints apply:</span></span>

- <span data-ttu-id="c0b7e-155">B1201: Источник надежного обмена сообщениями WCF всегда отправляет `CloseSequence` сообщение, чтобы завершить работу последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="c0b7e-156">B1202: источник системы надежного обмена сообщениями перед отправкой сообщения `CloseSequence` ждет подтверждения от всех сообщений последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="c0b7e-157">B1203: источник системы надежного обмена сообщениями всегда включает необязательный элемент `LastMsgNumber`, если в последовательности есть хотя бы одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="c0b7e-158">R1204: точка назначения системы надежного обмена сообщениями не должна инициировать закрытие последовательности путем отправки сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="c0b7e-159">B1205. После получения сообщения `CloseSequence` Источник надежного обмена сообщениями WCF считает последовательность незавершенной и отправляет ошибку.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="c0b7e-160">Пример сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-160">An example of a `CloseSequence` message.</span></span>

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

<span data-ttu-id="c0b7e-161">Пример сообщения `CloseSequenceResponse`:</span><span class="sxs-lookup"><span data-stu-id="c0b7e-161">Example `CloseSequenceResponse` message:</span></span>

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

### <a name="sequence-termination"></a><span data-ttu-id="c0b7e-162">Завершение последовательности</span><span class="sxs-lookup"><span data-stu-id="c0b7e-162">Sequence Termination</span></span>

<span data-ttu-id="c0b7e-163">WCF в основном использует `TerminateSequence/TerminateSequenceResponse`ное подтверждение связи после завершения `CloseSequence/CloseSequenceResponse` подтверждения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-163">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="c0b7e-164">Назначение надежного обмена сообщениями WCF не инициирует завершение и Источник надежного обмена сообщениями не поддерживает прерывание, инициированное адресатом.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-164">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="c0b7e-165">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-165">The following constraints apply:</span></span>

- <span data-ttu-id="c0b7e-166">B1301: инициатор WCF отправляет сообщение `TerminateSequence` только после успешного завершения подтверждения `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-166">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="c0b7e-167">R1302: WCF проверяет, что элемент `LastMsgNumber` согласован по всем `CloseSequence` и `TerminateSequence` сообщениям для данной последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-167">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="c0b7e-168">Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-168">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="c0b7e-169">B1303: при получении сообщения `TerminateSequence` после подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями отправляет в ответ сообщение `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-169">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c0b7e-170">Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-170">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="c0b7e-171">B1304: при получении сообщения `TerminateSequence` до `CloseSequence/CloseSequenceResponse` подтверждения, назначение надежного обмена сообщениями WCF реагирует на `TerminateSequenceResponse` сообщение.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-171">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="c0b7e-172">Если точка назначения системы надежного обмена сообщениями определяет, что в последовательности нет противоречий, она, прежде чем высвободить ресурсы, ждет в течение времени, заданного точкой назначения приложения, чтобы клиент мог получить последнее подтверждение.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-172">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="c0b7e-173">В противном случае точка назначения системы надежного обмена сообщениями сразу же высвобождает ресурсы и сообщает точке назначения приложения, что последовательность завершена, но не гарантированно, вызывая для этого событие `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-173">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="c0b7e-174">Пример сообщения `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-174">An example of a `TerminateSequence` message.</span></span>

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

<span data-ttu-id="c0b7e-175">Пример сообщения `TerminateSequenceResponse`:</span><span class="sxs-lookup"><span data-stu-id="c0b7e-175">Example `TerminateSequenceResponse` message:</span></span>

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

### <a name="sequences"></a><span data-ttu-id="c0b7e-176">Последовательности</span><span class="sxs-lookup"><span data-stu-id="c0b7e-176">Sequences</span></span>

<span data-ttu-id="c0b7e-177">Ниже приведен список ограничений, относящихся к последовательностям.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-177">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="c0b7e-178">B1401: WCF создает и обращается к порядковым номерам не выше максимального значения `xs:long`, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-178">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="c0b7e-179">Пример заголовка `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-179">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="c0b7e-180">Запрос подтверждения</span><span class="sxs-lookup"><span data-stu-id="c0b7e-180">Request Acknowledgement</span></span>

<span data-ttu-id="c0b7e-181">WCF использует заголовок `AckRequested` в качестве механизма поддержания активности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-181">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="c0b7e-182">Пример заголовка `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-182">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="c0b7e-183">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c0b7e-183">SequenceAcknowledgement</span></span>

<span data-ttu-id="c0b7e-184">WCF использует механизм свинка для подтверждения последовательностей, предоставляемых WS-надежный обмен сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-184">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="c0b7e-185">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-185">The following constraints apply:</span></span>

- <span data-ttu-id="c0b7e-186">R1601: Если две обратные последовательности установлены с помощью механизма `Offer`, заголовок `SequenceAcknowledgement` может быть добавлен в любое сообщение приложения, передаваемое предполагаемому получателю.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-186">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="c0b7e-187">Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-187">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="c0b7e-188">B1602: WCF не создает `SequenceAcknowledgement` заголовков, содержащих элементы `Nack`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-188">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="c0b7e-189">WCF проверяет, что каждый элемент `Nack` содержит порядковый номер, но в противном случае не учитывает `Nack` элемент и значение.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-189">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="c0b7e-190">Пример заголовка `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-190">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="c0b7e-191">Ошибки протокола WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="c0b7e-191">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="c0b7e-192">Ниже приведен список ограничений, которые применяются к реализации WCF ошибок WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-192">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="c0b7e-193">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-193">The following constraints apply:</span></span>

- <span data-ttu-id="c0b7e-194">B1701: WCF не создает `MessageNumberRollover` ошибок.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-194">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="c0b7e-195">B1702: по протоколу SOAP 1,2, когда конечная точка службы достигает предельного числа подключений и не может обработать новые соединения, WCF создает вложенный `CreateSequenceRefused` неисправного кода, `netrm:ConnectionLimitReached`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-195">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

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

### <a name="ws-addressing-faults"></a><span data-ttu-id="c0b7e-196">Ошибки WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="c0b7e-196">WS-Addressing Faults</span></span>

<span data-ttu-id="c0b7e-197">Поскольку WS-ReliableMessaging использует WS-Addressing, реализация WCF WS-ReliableMessaging может создавать и передавать ошибки WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-197">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="c0b7e-198">В этом разделе рассматриваются ошибки WS-Addressing, которые WCF явно создает и передает на уровне WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="c0b7e-198">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="c0b7e-199">B1801: WCF создает и передает ошибку `Message Addressing Header Required`, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-199">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="c0b7e-200">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;</span><span class="sxs-lookup"><span data-stu-id="c0b7e-200">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="c0b7e-201">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;</span><span class="sxs-lookup"><span data-stu-id="c0b7e-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="c0b7e-202">в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-202">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="c0b7e-203">B1802: WCF создает и передает ошибку `Endpoint Unavailable`, чтобы указать, что не существует прослушивания конечных точек, которое может обработать последовательность на основе проверки заголовков адресации в сообщении `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-203">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="c0b7e-204">Сочетаемость протокола</span><span class="sxs-lookup"><span data-stu-id="c0b7e-204">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="c0b7e-205">Сочетаемость с WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="c0b7e-205">Composition with WS-Addressing</span></span>

<span data-ttu-id="c0b7e-206">WCF поддерживает две версии WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации консорциума W3C WS-Addressing 1,0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="c0b7e-206">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="c0b7e-207">Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-207">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="c0b7e-208">Ниже приведен список ограничений, применяемых к WCF.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-208">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c0b7e-209">R2101: с протоколом WS-ReliableMessaging можно использовать как версию WS-Addressing 2004/08, так и версию WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-209">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="c0b7e-210">R2102: в рамках заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью механизма `Offer`, следует использовать только одну версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-210">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="c0b7e-211">Сочетаемость с SOAP</span><span class="sxs-lookup"><span data-stu-id="c0b7e-211">Composition with SOAP</span></span>

<span data-ttu-id="c0b7e-212">WCF поддерживает использование SOAP 1,1 и SOAP 1,2 с WS-надежный обмен сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-212">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="c0b7e-213">Сочетаемость с WS-Security и WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="c0b7e-213">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="c0b7e-214">WCF обеспечивает защиту для последовательностей WS-ReliableMessaging с помощью защищенного транспорта (HTTPS), композиции с WS-Security и компоновки с WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-214">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="c0b7e-215">Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-215">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="c0b7e-216">Ниже приведен список ограничений, применяемых к WCF.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-216">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c0b7e-217">R2301. чтобы защитить целостность последовательности WS-ReliableMessaging в дополнение к целостности и конфиденциальности отдельных сообщений, WCF требует, чтобы использовался протокол WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-217">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="c0b7e-218">R2302:перед установкой последовательностей WS-ReliableMessagingдолжен быть установлен сеанс WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-218">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="c0b7e-219">R2303: если время существования последовательности WS-ReliableMessaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-219">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="c0b7e-220">B2304:последовательность WS-ReliableMessaging или пара встречных последовательностей всегда связаны с одним сеансом WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-220">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="c0b7e-221">R2305. при сопоставлении с WS-Secure conversations для WCF требуется, чтобы `CreateSequence` сообщение содержало элемент `wsse:SecurityTokenReference` и заголовок `wsrm:UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-221">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="c0b7e-222">Пример заголовка `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-222">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="c0b7e-223">Сочетаемость с сеансами SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="c0b7e-223">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="c0b7e-224">WCF не поддерживает композицию для сеансов SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="c0b7e-224">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="c0b7e-225">B2401: WCF не создает заголовок `wsrm:UsesSequenceSSL`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-225">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="c0b7e-226">R2402: инициатор надежного обмена сообщениями не должен передавать сообщение `CreateSequence` с заголовком `wsrm:UsesSequenceSSL` в ответчик WCF.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-226">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="c0b7e-227">Сочетаемость с WS-Policy</span><span class="sxs-lookup"><span data-stu-id="c0b7e-227">Composition with WS-Policy</span></span>

<span data-ttu-id="c0b7e-228">WCF поддерживает две версии WS-Policy: WS-Policy 1,2 и WS-Policy 1,5.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-228">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="c0b7e-229">Утверждение WS-ReliableMessaging WS-Policy</span><span class="sxs-lookup"><span data-stu-id="c0b7e-229">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="c0b7e-230">Для описания возможностей конечных точек WCF использует утверждение WS-ReliableMessaging WS-Policy `wsrm:RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-230">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="c0b7e-231">Ниже приведен список ограничений, применяемых к WCF.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-231">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c0b7e-232">B3001: WCF присоединяет `wsrmn:RMAssertion` утверждения WS-Policy к `wsdl:binding`ным элементам.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-232">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="c0b7e-233">WCF поддерживает оба вложения для `wsdl:binding` и `wsdl:port` элементов.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-233">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="c0b7e-234">B3002: WCF никогда не создает тег `wsp:Optional`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-234">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="c0b7e-235">B3003. при доступе к утверждению `wsrmp:RMAssertion` WS-Policy WCF игнорирует тег `wsp:Optional` и обрабатывает политику WS-RM как обязательную.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-235">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="c0b7e-236">R3004: поскольку WCF не сопоставлена с сеансами SSL/TLS, WCF не принимает политику, задающую `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-236">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="c0b7e-237">B3005: WCF всегда создает элемент `wsrmp:DeliveryAssurance`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-237">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="c0b7e-238">B3006. в WCF всегда указывается гарантия доставки `wsrmp:ExactlyOnce`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-238">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="c0b7e-239">B3007: WCF создает и считывает следующие свойства утверждения WS-ReliableMessaging и обеспечивает контроль над ними в`ReliableSessionBindingElement`WCF:</span><span class="sxs-lookup"><span data-stu-id="c0b7e-239">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="c0b7e-240">Пример `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-240">An example of a `RMAssertion`.</span></span>

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

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="c0b7e-241">Расширение WS-ReliableMessaging для управления потоком</span><span class="sxs-lookup"><span data-stu-id="c0b7e-241">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="c0b7e-242">WCF использует расширяемость WS-ReliableMessaging для предоставления дополнительного более строгого контроля над потоком сообщений последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-242">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="c0b7e-243">Управление потоком включается путем присвоения свойству <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> значения `true`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-243">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="c0b7e-244">Ниже приведен список ограничений, применяемых к WCF.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-244">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="c0b7e-245">B4001. при включении управления потоком надежного обмена сообщениями WCF создает элемент `netrm:BufferRemaining` в расширяемости элемента заголовка `SequenceAcknowledgement`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-245">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="c0b7e-246">B4002. даже если включен механизм надежного управления потоком сообщений, WCF не требует элемент `netrm:BufferRemaining` в заголовке `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-246">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="c0b7e-247">B4003: в назначении надежного обмена сообщениями WCF используется `netrm:BufferRemaining`, чтобы указать, сколько новых сообщений может быть помещено в буфер.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-247">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="c0b7e-248">B4004. при включении управления потоком надежного обмена сообщениями Источник надежного обмена сообщениями WCF использует значение `netrm:BufferRemaining` для регулирования передачи сообщений.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-248">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="c0b7e-249">B4005: WCF создает `netrm:BufferRemaining` целочисленных значений от 0 до 4096 включительно и считывает целочисленные значения от 0 до `xs:int``maxInclusive` значение 214748364 включительно.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-249">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="c0b7e-250">Шаблоны обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="c0b7e-250">Message Exchange Patterns</span></span>

<span data-ttu-id="c0b7e-251">В этом разделе описывается поведение WCF при использовании WS-ReliableMessaging для различных шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-251">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="c0b7e-252">Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:</span><span class="sxs-lookup"><span data-stu-id="c0b7e-252">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="c0b7e-253">неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;</span><span class="sxs-lookup"><span data-stu-id="c0b7e-253">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="c0b7e-254">адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-254">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="c0b7e-255">Односторонний неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="c0b7e-255">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c0b7e-256">Привязка</span><span class="sxs-lookup"><span data-stu-id="c0b7e-256">Binding</span></span>

<span data-ttu-id="c0b7e-257">WCF предоставляет односторонний шаблон обмена сообщениями, используя одну последовательность по одному каналу HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-257">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="c0b7e-258">WCF использует HTTP-запросы для передачи всех сообщений от инициатора в ответчик и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-258">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c0b7e-259">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-259">CreateSequence Exchange</span></span>

<span data-ttu-id="c0b7e-260">Инициатор WCF передает `CreateSequence` сообщение без элемента `Offer` в HTTP-запросе и ждет сообщения `CreateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-260">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c0b7e-261">WCF-ответчик создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-261">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="c0b7e-262">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="c0b7e-262">SequenceAcknowledgement</span></span>

<span data-ttu-id="c0b7e-263">Инициатор WCF обрабатывает подтверждения по ответу всех сообщений, за исключением `CreateSequence` сообщения и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-263">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="c0b7e-264">WCF-ответчик всегда передает изолированное подтверждение ответа HTTP всем последовательностью и `AckRequested` сообщениям.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-264">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="c0b7e-265">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-265">CloseSequence Exchange</span></span>

<span data-ttu-id="c0b7e-266">Инициатор WCF передает `CloseSequence` сообщение в HTTP-запросе и ждет сообщения `CreateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-266">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c0b7e-267">WCF-ответчик передает `CloseSequenceResponse` сообщение в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-267">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c0b7e-268">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-268">TerminateSequence Exchange</span></span>

<span data-ttu-id="c0b7e-269">Инициатор WCF передает `TerminateSequence` сообщение в HTTP-запросе и ждет сообщения `TerminateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-269">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c0b7e-270">WCF-ответчик передает `TerminateSequenceResponse` сообщение в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-270">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="c0b7e-271">Односторонний адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="c0b7e-271">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c0b7e-272">Привязка</span><span class="sxs-lookup"><span data-stu-id="c0b7e-272">Binding</span></span>

<span data-ttu-id="c0b7e-273">WCF предоставляет односторонний шаблон обмена сообщениями, используя одну последовательность для одного входящего и одного исходящего HTTP-канала.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-273">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c0b7e-274">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-274">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c0b7e-275">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-275">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c0b7e-276">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-276">CreateSequence Exchange</span></span>

<span data-ttu-id="c0b7e-277">Инициатор WCF передает `CreateSequence` сообщение без элемента `Offer` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-277">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c0b7e-278">WCF-ответчик создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в запросе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-278">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="c0b7e-279">Дуплексный адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="c0b7e-279">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c0b7e-280">Привязка</span><span class="sxs-lookup"><span data-stu-id="c0b7e-280">Binding</span></span>

<span data-ttu-id="c0b7e-281">WCF предоставляет полностью асинхронный, двусторонний шаблон обмена сообщениями с использованием двух последовательностей по одному входящему и одному исходящему каналу HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-281">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c0b7e-282">Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-282">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="c0b7e-283">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-283">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c0b7e-284">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-284">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c0b7e-285">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-285">CreateSequence Exchange</span></span>

<span data-ttu-id="c0b7e-286">Инициатор WCF передает `CreateSequence` сообщение с элементом `Offer` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-286">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c0b7e-287">WCF-ответчик гарантирует, что `CreateSequence` имеет элемент `Offer`, затем создает последовательность и передает `CreateSequenceResponse` сообщение с помощью элемента `Accept`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-287">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="c0b7e-288">Время существования последовательности</span><span class="sxs-lookup"><span data-stu-id="c0b7e-288">Sequence Lifetime</span></span>

<span data-ttu-id="c0b7e-289">WCF рассматривает две последовательности как один полностью дуплексный сеанс.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-289">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="c0b7e-290">При создании ошибки, которая не выполняет одну последовательность, WCF ждет, что удаленная конечная точка будет выполнять обе последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-290">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="c0b7e-291">При чтении ошибки, которая не выполняет одну последовательность, WCF завершает обе последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-291">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="c0b7e-292">WCF может закрыть свою исходящую последовательность и продолжить обработку сообщений на его входящей последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-292">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="c0b7e-293">И наоборот, WCF может обработать закрытие входящей последовательности и продолжить отправку сообщений по исходящей последовательности.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-293">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="c0b7e-294">Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="c0b7e-294">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c0b7e-295">Привязка</span><span class="sxs-lookup"><span data-stu-id="c0b7e-295">Binding</span></span>

<span data-ttu-id="c0b7e-296">WCF предоставляет односторонний шаблон обмена сообщениями типа «запрос-ответ» с использованием двух последовательностей по одному каналу HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-296">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="c0b7e-297">WCF использует HTTP-запросы для передачи всех сообщений от инициатора в ответчик и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-297">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c0b7e-298">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-298">CreateSequence Exchange</span></span>

<span data-ttu-id="c0b7e-299">Инициатор WCF передает `CreateSequence` сообщение с элементом `Offer` в HTTP-запросе и ждет сообщения `CreateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-299">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="c0b7e-300">WCF-ответчик создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept` в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-300">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="c0b7e-301">Односторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="c0b7e-301">One-way Message</span></span>

<span data-ttu-id="c0b7e-302">Чтобы успешно завершить односторонний обмен сообщениями, инициатор WCF передает сообщение последовательности запроса по HTTP-запросу и получает автономное сообщение `SequenceAcknowledgement` в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-302">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="c0b7e-303">Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-303">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="c0b7e-304">Ответчик WCF может ответить на запрос с помощью подтверждения, ошибки или ответа с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-304">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="c0b7e-305">Двусторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="c0b7e-305">Two Way Messages</span></span>

<span data-ttu-id="c0b7e-306">Для успешного завершения двустороннего обмена сообщениями инициатор WCF передает сообщение последовательности запросов по HTTP-запросу и получает сообщение последовательности ответов в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-306">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="c0b7e-307">Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-307">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="c0b7e-308">Ответчик WCF может ответить на запрос с ответом на приложение, ошибку или ответ с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-308">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="c0b7e-309">Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-309">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="c0b7e-310">Повторные попытки ответов</span><span class="sxs-lookup"><span data-stu-id="c0b7e-310">Retrying Replies</span></span>

<span data-ttu-id="c0b7e-311">WCF использует корреляцию HTTP-ответа "запрос — ответ" для двусторонней корреляции протокола обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-311">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="c0b7e-312">По этой причине инициатор WCF не прекращает повторную попытку сообщения последовательности запроса, когда сообщение последовательностей запроса подтверждено, а когда HTTP-ответ содержит `SequenceAcknowledgement`, ответ приложения или ошибку.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-312">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="c0b7e-313">WCF-ответчик повторяет ответы в ответе HTTP запроса, к которому коррелирован ответ.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-313">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="c0b7e-314">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-314">CloseSequence Exchange</span></span>

<span data-ttu-id="c0b7e-315">После получения всех сообщений последовательности ответов и подтверждений для всех однонаправленных сообщений последовательности запросов инициатор WCF передает `CloseSequence` сообщение для последовательности запросов по HTTP-запросу и ожидает `CloseSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-315">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="c0b7e-316">Закрытие последовательности запросов неявным образом закрывает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-316">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="c0b7e-317">Это означает, что инициатор WCF включает окончательный `SequenceAcknowledgement` в `CloseSequence` сообщении, а последовательность ответов не имеет `CloseSequence` Exchange.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-317">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="c0b7e-318">WCF-ответчик гарантирует, что все ответы будут подтверждены, и передает `CloseSequenceResponse` сообщение в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-318">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="c0b7e-319">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-319">TerminateSequence Exchange</span></span>

<span data-ttu-id="c0b7e-320">После получения сообщения `CloseSequenceResponse` инициатор WCF передает `TerminateSequence` сообщение для последовательности запроса по HTTP-запросу и ожидает `TerminateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-320">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="c0b7e-321">Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-321">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="c0b7e-322">Это означает, что инициатор WCF включает окончательный `SequenceAcknowledgement` в `TerminateSequence` сообщении, а последовательность ответов не имеет `TerminateSequence` Exchange.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-322">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="c0b7e-323">WCF-ответчик передает `TerminateSequenceResponse` сообщение в ответе HTTP.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-323">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="c0b7e-324">Обмен сообщениями запрос-ответ, адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="c0b7e-324">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="c0b7e-325">Привязка</span><span class="sxs-lookup"><span data-stu-id="c0b7e-325">Binding</span></span>

<span data-ttu-id="c0b7e-326">WCF предоставляет шаблон обмена сообщениями типа «запрос-ответ» с использованием двух последовательностей по одному входящему и одному исходящему HTTP-каналу.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-326">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="c0b7e-327">Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-327">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="c0b7e-328">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-328">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="c0b7e-329">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-329">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="c0b7e-330">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="c0b7e-330">CreateSequence Exchange</span></span>

<span data-ttu-id="c0b7e-331">Инициатор WCF передает `CreateSequence` сообщение с элементом `Offer` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-331">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="c0b7e-332">WCF-ответчик гарантирует, что `CreateSequence` имеет `Offer` элемент, затем создает последовательность и передает `CreateSequenceResponse` сообщение с элементом `Accept`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-332">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="c0b7e-333">Корреляция запросов и ответов</span><span class="sxs-lookup"><span data-stu-id="c0b7e-333">Request/Reply Correlation</span></span>

<span data-ttu-id="c0b7e-334">Следующие действия относятся ко всем связанным запросам и ответам.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-334">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="c0b7e-335">WCF гарантирует, что все сообщения запроса приложения по`ReplyTo` ссылку на конечную точку и `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-335">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="c0b7e-336">WCF применяет ссылку на локальную конечную точку в качестве `ReplyTo`сообщения запроса приложения.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-336">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="c0b7e-337">Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-337">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="c0b7e-338">WCF гарантирует, что входящие сообщения запроса поставили `MessageId` и `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-338">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="c0b7e-339">WCF гарантирует, что URI ссылки на конечную точку `ReplyTo` всех сообщений запроса приложения соответствует ссылке на локальную конечную точку, как определено ранее.</span><span class="sxs-lookup"><span data-stu-id="c0b7e-339">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="c0b7e-340">WCF гарантирует, что все ответы представили правильные `RelatesTo` и `To` заголовки, следующие `wsa` правил корреляции "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="c0b7e-340">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
