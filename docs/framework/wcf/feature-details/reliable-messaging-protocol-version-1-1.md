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
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="2a48a-102">Протокол надежного обмена сообщениями, версия 1,1</span><span class="sxs-lookup"><span data-stu-id="2a48a-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="2a48a-103">В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для протокола WS-ReliableMessaging протокола февраля 2007 г. (версия 1.1), необходимые для взаимодействия с использованием транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="2a48a-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="2a48a-104">WCF соответствует спецификации WS-ReliableMessaging с определенными ограничениями и пояснениями, описанными далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="2a48a-105">Обратите внимание, что реализуется начиная с версии 1.1 протокола WS-ReliableMessaging [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a48a-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="2a48a-106">WS-ReliableMessaging февраля 2007 г. протокол реализуется в WCF с <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2a48a-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="2a48a-107">Для удобства объяснения в этом разделе используются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="2a48a-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="2a48a-108">инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;</span><span class="sxs-lookup"><span data-stu-id="2a48a-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="2a48a-109">респондент: служба, получающая запросы инициатора.</span><span class="sxs-lookup"><span data-stu-id="2a48a-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="2a48a-110">В этом документе используются префиксы и пространства имен, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2a48a-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="2a48a-111">Префикс</span><span class="sxs-lookup"><span data-stu-id="2a48a-111">Prefix</span></span>|<span data-ttu-id="2a48a-112">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="2a48a-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="2a48a-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="2a48a-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|<span data-ttu-id="2a48a-114">netrm</span><span class="sxs-lookup"><span data-stu-id="2a48a-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="2a48a-115">s</span><span class="sxs-lookup"><span data-stu-id="2a48a-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="2a48a-116">wsa</span><span class="sxs-lookup"><span data-stu-id="2a48a-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="2a48a-117">wsse</span><span class="sxs-lookup"><span data-stu-id="2a48a-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="2a48a-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="2a48a-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|<span data-ttu-id="2a48a-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="2a48a-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|<span data-ttu-id="2a48a-120">wsp</span><span class="sxs-lookup"><span data-stu-id="2a48a-120">wsp</span></span>|<span data-ttu-id="2a48a-121">(WS-Policy 1.2 или WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="2a48a-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="2a48a-122">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="2a48a-122">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="2a48a-123">Создание последовательности</span><span class="sxs-lookup"><span data-stu-id="2a48a-123">Sequence Creation</span></span>  
 <span data-ttu-id="2a48a-124">Реализует WCF `CreateSequence` и `CreateSequenceResponse` последовательности сообщений для установления надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2a48a-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="2a48a-125">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-125">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2a48a-126">B1101: Инициатор WCF использует ту же ссылку конечной точки, как `CreateSequence` сообщения `ReplyTo`, `AcksTo` и `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="2a48a-127">R1102: адреса ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь идентичные строковые представления, чтобы они совпадали на уровне октетов.</span><span class="sxs-lookup"><span data-stu-id="2a48a-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="2a48a-128">Респондент WCF проверяет, что URI части `AcksTo`, `ReplyTo` и `Endpoint` идентичны ссылки на конечные точки перед созданием последовательности.</span><span class="sxs-lookup"><span data-stu-id="2a48a-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="2a48a-129">R1103: ссылки на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.</span><span class="sxs-lookup"><span data-stu-id="2a48a-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="2a48a-130">WCF не применяет принудительно, но предполагается, что ссылка параметры `AcksTo`, `ReplyTo` и `Offer/Endpoint` ссылок на `CreateSequence` идентичны и используются параметры `ReplyTo` ссылки на конечную точку для подтверждениях и сообщениях встречной последовательности.</span><span class="sxs-lookup"><span data-stu-id="2a48a-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="2a48a-131">B1104: Инициатор WCF не создает необязательный `Expires` или `Offer/Expires` элемент в `CreateSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="2a48a-132">B1105: При доступе к `CreateSequence` сообщение, отвечающая сторона WCF использует `Expires` значение в `CreateSequence` элемент как `Expires` значение в `CreateSequenceResponse` элемент.</span><span class="sxs-lookup"><span data-stu-id="2a48a-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="2a48a-133">В противном случае респондент WCF считывает и игнорирует `Expires` и `Offer/Expires` значения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="2a48a-134">B1106: При доступе к `CreateSequenceResponse` сообщения WCF инициатора считывает необязательное `Expires` значение, но не используется.</span><span class="sxs-lookup"><span data-stu-id="2a48a-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="2a48a-135">B1107: Инициатор WCF и отвечающее устройство всегда создают необязательный `IncompleteSequenceBehavior` элемент в `CreateSequence/Offer` и `CreateSequenceResponse` элементы.</span><span class="sxs-lookup"><span data-stu-id="2a48a-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="2a48a-136">B1108: WCF использует только `DiscardFollowingFirstGap` и `NoDiscard` значения в `IncompleteSequenceBehavior` элемент.</span><span class="sxs-lookup"><span data-stu-id="2a48a-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="2a48a-137">Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.</span><span class="sxs-lookup"><span data-stu-id="2a48a-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="2a48a-138">B1109: Если `CreateSequence` содержит `Offer` элемент, одним из способов WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceResponse` без `Accept` элемента.</span><span class="sxs-lookup"><span data-stu-id="2a48a-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="2a48a-139">B1110: Если респондент отклоняет предложенную последовательность, инициатор WCF ошибках последовательность.</span><span class="sxs-lookup"><span data-stu-id="2a48a-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="2a48a-140">B1111: Если `CreateSequence` не содержит `Offer` элемент, двустороннее WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceRefused` ошибки.</span><span class="sxs-lookup"><span data-stu-id="2a48a-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="2a48a-141">R1112: при установке с помощью механизма `Offer` двух встречных последовательностей, свойство `[address]` ссылки на конечную точку `CreateSequenceResponse/Accept/AcksTo` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="2a48a-142">R1113: при установке с помощью механизма `Offer` двух встречных последовательностей, все сообщения от инициатора к респонденту в обеих последовательностях должны отправляться по одной и той же ссылке на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="2a48a-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="2a48a-143">WCF использует WS-ReliableMessaging для установки надежных сеансов между инициатором и респондентом.</span><span class="sxs-lookup"><span data-stu-id="2a48a-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="2a48a-144">Реализация WS-ReliableMessaging, WCF обеспечивает создание надежного сеанса для односторонней связи, запрос ответ и полный двустороннего обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2a48a-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="2a48a-145">Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2a48a-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="2a48a-146">Поскольку WCF гарантирует безопасность таких сеансов, включая защиты от начала до конца для обеспечения целостности сеанса, это целесообразно, чтобы убедиться, что сообщения, предназначенные для той же стороне доставлены в одном месте назначения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="2a48a-147">Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений.</span><span class="sxs-lookup"><span data-stu-id="2a48a-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="2a48a-148">Таким образом R1102, R1112 и R1113 ограничения для WCF.</span><span class="sxs-lookup"><span data-stu-id="2a48a-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>  
  
 <span data-ttu-id="2a48a-149">Пример сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-149">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="2a48a-150">Пример сообщения `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-150">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="2a48a-151">Закрытие последовательности</span><span class="sxs-lookup"><span data-stu-id="2a48a-151">Closing a Sequence</span></span>  
 <span data-ttu-id="2a48a-152">WCF использует `CloseSequence` и `CloseSequenceResponse` сообщений для завершения инициативе источника системы надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2a48a-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="2a48a-153">Назначения надежного обмена сообщениями WCF не инициирует завершение работы и Источник надежного обмена сообщениями WCF не поддерживает выключение инициируемое точкой назначения надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2a48a-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="2a48a-154">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-154">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2a48a-155">B1201: Источник надежного обмена сообщениями WCF всегда отправляет `CloseSequence` сообщение закрытия последовательности.</span><span class="sxs-lookup"><span data-stu-id="2a48a-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="2a48a-156">B1202: источник системы надежного обмена сообщениями перед отправкой сообщения `CloseSequence` ждет подтверждения от всех сообщений последовательности.</span><span class="sxs-lookup"><span data-stu-id="2a48a-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="2a48a-157">B1203: источник системы надежного обмена сообщениями всегда включает необязательный элемент `LastMsgNumber`, если в последовательности есть хотя бы одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="2a48a-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="2a48a-158">R1204: точка назначения системы надежного обмена сообщениями не должна инициировать закрытие последовательности путем отправки сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="2a48a-159">B1205: после получения `CloseSequence` сообщение, Источник надежного обмена сообщениями WCF считает, что последовательность неполными и отправляет ошибку.</span><span class="sxs-lookup"><span data-stu-id="2a48a-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="2a48a-160">Пример сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-160">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="2a48a-161">Завершение последовательности</span><span class="sxs-lookup"><span data-stu-id="2a48a-161">Sequence Termination</span></span>  
 <span data-ttu-id="2a48a-162">WCF в основном используется `TerminateSequence/TerminateSequenceResponse` подтверждения после завершения `CloseSequence/CloseSequenceResponse` подтверждения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-162">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="2a48a-163">Назначения надежного обмена сообщениями WCF не инициирует завершение и источник системы надежного обмена сообщениями не поддерживает завершение инициируемое точкой назначения надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2a48a-163">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="2a48a-164">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-164">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2a48a-165">B1301: Инициатор WCF только отправляет `TerminateSequence` сообщение после успешного завершения `CloseSequence/CloseSequenceResponse` подтверждения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-165">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="2a48a-166">R1302: WCF проверяет, что `LastMsgNumber` элемент одинаков во всех `CloseSequence` и `TerminateSequence` сообщений для заданной последовательности.</span><span class="sxs-lookup"><span data-stu-id="2a48a-166">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="2a48a-167">Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-167">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="2a48a-168">B1303: при получении сообщения `TerminateSequence` после подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями отправляет в ответ сообщение `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-168">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="2a48a-169">Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.</span><span class="sxs-lookup"><span data-stu-id="2a48a-169">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="2a48a-170">B1304: При получении `TerminateSequence` сообщений до `CloseSequence/CloseSequenceResponse` подтверждения назначения надежного обмена сообщениями WCF отвечает `TerminateSequenceResponse` сообщения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-170">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="2a48a-171">Если точка назначения системы надежного обмена сообщениями определяет, что в последовательности нет противоречий, она, прежде чем высвободить ресурсы, ждет в течение времени, заданного точкой назначения приложения, чтобы клиент мог получить последнее подтверждение.</span><span class="sxs-lookup"><span data-stu-id="2a48a-171">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="2a48a-172">В противном случае точка назначения системы надежного обмена сообщениями сразу же высвобождает ресурсы и сообщает точке назначения приложения, что последовательность завершена, но не гарантированно, вызывая для этого событие `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-172">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="2a48a-173">Пример сообщения `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-173">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="2a48a-174">Последовательности</span><span class="sxs-lookup"><span data-stu-id="2a48a-174">Sequences</span></span>  
 <span data-ttu-id="2a48a-175">Ниже приведен список ограничений, относящихся к последовательностям.</span><span class="sxs-lookup"><span data-stu-id="2a48a-175">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="2a48a-176">Создает B1401:WCF и обращается к порядковых номеров, не превышает `xs:long`максимальное значение включительно, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="2a48a-176">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="2a48a-177">Пример заголовка `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-177">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="2a48a-178">Запрос подтверждения</span><span class="sxs-lookup"><span data-stu-id="2a48a-178">Request Acknowledgement</span></span>  
 <span data-ttu-id="2a48a-179">WCF использует `AckRequested` заголовок как механизм поддержания активности.</span><span class="sxs-lookup"><span data-stu-id="2a48a-179">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="2a48a-180">Пример заголовка `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-180">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="2a48a-181">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="2a48a-181">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="2a48a-182">WCF использует механизм «делает обратной» для передачи подтверждений последовательностей в WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="2a48a-182">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="2a48a-183">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-183">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2a48a-184">R1601: При установке двух встречных последовательностей, устанавливаются с помощью `Offer` механизм, `SequenceAcknowledgement` заголовок может быть включено в любое сообщение приложения, передаваемых предполагаемому получателю.</span><span class="sxs-lookup"><span data-stu-id="2a48a-184">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="2a48a-185">Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-185">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="2a48a-186">B1602: WCF не создает `SequenceAcknowledgement` заголовков, содержащих `Nack` элементов.</span><span class="sxs-lookup"><span data-stu-id="2a48a-186">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="2a48a-187">WCF проверяет, каждая из которых `Nack` элемент содержит порядковый номер, но в противном случае значение не учитывает `Nack` элементом и значением.</span><span class="sxs-lookup"><span data-stu-id="2a48a-187">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="2a48a-188">Пример заголовка `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-188">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="2a48a-189">Ошибки протокола WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="2a48a-189">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="2a48a-190">Ниже приведен список ограничений, относящихся к реализации WCF ошибки протокола WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="2a48a-190">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="2a48a-191">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-191">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="2a48a-192">B1701: WCF не создает `MessageNumberRollover` ошибок.</span><span class="sxs-lookup"><span data-stu-id="2a48a-192">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="2a48a-193">B1702: В SOAP 1.2, когда конечной точки службы достигает этого значения подключения и не может обработать новые подключения, WCF создает вложенный `CreateSequenceRefused` код, ошибки `netrm:ConnectionLimitReached`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a48a-193">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="2a48a-194">Ошибки WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="2a48a-194">WS-Addressing Faults</span></span>  
 <span data-ttu-id="2a48a-195">Так как WS-ReliableMessaging использует протокол WS-Addressing, реализация WS-ReliableMessaging, WCF может создавать и передавать ошибки WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="2a48a-195">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="2a48a-196">В этом разделе описаны ошибки WS-Addressing, которые WCF явным образом создает и передает на уровне WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="2a48a-196">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="2a48a-197">B1801:WCF создает и передает `Message Addressing Header Required` сбоя при выполнении одного из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2a48a-197">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="2a48a-198">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;</span><span class="sxs-lookup"><span data-stu-id="2a48a-198">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="2a48a-199">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;</span><span class="sxs-lookup"><span data-stu-id="2a48a-199">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="2a48a-200">в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-200">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="2a48a-201">B1802:WCF создает и передает `Endpoint Unavailable` ошибки для указания отсутствует конечная точка ожидает передачи данных, который может обрабатывать последовательности, основанной на изучение заголовки адресации в `CreateSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-201">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="2a48a-202">Сочетаемость протокола</span><span class="sxs-lookup"><span data-stu-id="2a48a-202">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="2a48a-203">Сочетаемость с WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="2a48a-203">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="2a48a-204">WCF поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации W3C WS-Addressing 1.0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="2a48a-204">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="2a48a-205">Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="2a48a-205">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="2a48a-206">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="2a48a-206">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2a48a-207">R2101: с протоколом WS-ReliableMessaging можно использовать как версию WS-Addressing 2004/08, так и версию WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="2a48a-207">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="2a48a-208">R2102: в рамках заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью механизма `Offer`, следует использовать только одну версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="2a48a-208">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="2a48a-209">Сочетаемость с SOAP</span><span class="sxs-lookup"><span data-stu-id="2a48a-209">Composition with SOAP</span></span>  
 <span data-ttu-id="2a48a-210">WCF поддерживает использование SOAP 1.1 и SOAP 1.2 с WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="2a48a-210">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="2a48a-211">Сочетаемость с WS-Security и WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="2a48a-211">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="2a48a-212">WCF обеспечивает защиту последовательностей WS-ReliableMessaging с помощью безопасного транспорта (HTTPS), сочетаемость с WS-Security и сочетаемость с WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="2a48a-212">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="2a48a-213">Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="2a48a-213">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="2a48a-214">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="2a48a-214">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2a48a-215">R2301: Для защиты целостности последовательности WS-ReliableMessaging, помимо целостности и конфиденциальности отдельных сообщений, WCF требуется должен использоваться WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="2a48a-215">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="2a48a-216">R2302:AWS-Secure Conversation должен быть установлен до установки последовательностях WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="2a48a-216">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="2a48a-217">R2303: если время существования последовательности WS-ReliableMessaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="2a48a-217">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="2a48a-218">B2304:ws-последовательности ReliableMessaging или пары коррелированные встречные последовательности всегда привязан к одного сеанса WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="2a48a-218">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="2a48a-219">R2305: При создании WS-Secure Conversation респондент WCF требуется `CreateSequence` сообщение содержит `wsse:SecurityTokenReference` элемент и `wsrm:UsesSequenceSTR` заголовок.</span><span class="sxs-lookup"><span data-stu-id="2a48a-219">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="2a48a-220">Пример заголовка `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-220">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="2a48a-221">Сочетаемость с сеансами SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="2a48a-221">Composition with SSL/TLS sessions</span></span>  
 <span data-ttu-id="2a48a-222">WCF не поддерживает сочетаемость с сеансами SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="2a48a-222">WCF does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="2a48a-223">B2401: WCF не создает `wsrm:UsesSequenceSSL` заголовок.</span><span class="sxs-lookup"><span data-stu-id="2a48a-223">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="2a48a-224">R2402: Инициатор С надежного обмена сообщениями не должен отправлять `CreateSequence` сообщений с `wsrm:UsesSequenceSSL` заголовок, чтобы респондент WCF.</span><span class="sxs-lookup"><span data-stu-id="2a48a-224">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="2a48a-225">Сочетаемость с WS-Policy</span><span class="sxs-lookup"><span data-stu-id="2a48a-225">Composition with WS-Policy</span></span>  
 <span data-ttu-id="2a48a-226">WCF поддерживает две версии протокола WS-Policy: WS-Policy 1.2 и WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="2a48a-226">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="2a48a-227">Утверждение WS-ReliableMessaging WS-Policy</span><span class="sxs-lookup"><span data-stu-id="2a48a-227">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="2a48a-228">WCF использует утверждение WS-ReliableMessaging WS-Policy `wsrm:RMAssertion` для описания возможностей конечных точек.</span><span class="sxs-lookup"><span data-stu-id="2a48a-228">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="2a48a-229">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="2a48a-229">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2a48a-230">B3001: Присоединяет WCF `wsrmn:RMAssertion` утверждение WS-Policy для `wsdl:binding` элементов.</span><span class="sxs-lookup"><span data-stu-id="2a48a-230">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="2a48a-231">WCF поддерживает вложения в `wsdl:binding` и `wsdl:port` элементы.</span><span class="sxs-lookup"><span data-stu-id="2a48a-231">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="2a48a-232">B3002: WCF никогда не приводит к возникновению ошибки `wsp:Optional` тег.</span><span class="sxs-lookup"><span data-stu-id="2a48a-232">B3002: WCF never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="2a48a-233">B3003: При доступе к `wsrmp:RMAssertion` утверждение WS-Policy WCF игнорирует `wsp:Optional` теги и трактует политику WS-RM как обязательную.</span><span class="sxs-lookup"><span data-stu-id="2a48a-233">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="2a48a-234">R3004: Поскольку WCF не составить с сеансами SSL/TLS, WCF не принимает политики, задающие `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-234">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="2a48a-235">B3005: WCF всегда приводит к возникновению ошибки `wsrmp:DeliveryAssurance` элемента.</span><span class="sxs-lookup"><span data-stu-id="2a48a-235">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="2a48a-236">B3006: WCF всегда указывает `wsrmp:ExactlyOnce` гарантии доставки.</span><span class="sxs-lookup"><span data-stu-id="2a48a-236">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="2a48a-237">B3007: WCF приводит к возникновению ошибки и считывает следующие свойства утверждения WS-ReliableMessaging и реализует контроль над ними в WCF`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="2a48a-237">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="2a48a-238">Пример `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-238">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="2a48a-239">Расширение WS-ReliableMessaging для управления потоком</span><span class="sxs-lookup"><span data-stu-id="2a48a-239">Flow Control WS-ReliableMessaging Extension</span></span>  
 <span data-ttu-id="2a48a-240">WCF использует расширяемость WS-ReliableMessaging для обеспечения более строгий контроль над потоком последовательности сообщений.</span><span class="sxs-lookup"><span data-stu-id="2a48a-240">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="2a48a-241">Включить управление потоком, задав `ReliableSessionBindingElement` `FlowControlEnabled``boolean` свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-241">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="2a48a-242">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="2a48a-242">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="2a48a-243">B4001: Если включена надежного обмена сообщениями потока управления, WCF приводит к возникновению ошибки `netrm:BufferRemaining` элемент расширения элемента `SequenceAcknowledgement` заголовок, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a48a-243">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="2a48a-244">B4002: Даже в том случае, если включена надежного обмена сообщениями потока управления, WCF не требует `netrm:BufferRemaining` элемент в `SequenceAcknowledgement` заголовок.</span><span class="sxs-lookup"><span data-stu-id="2a48a-244">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="2a48a-245">B4003: Назначения надежного обмена сообщениями WCF использует `netrm:BufferRemaining` для указания того, сколько новых сообщений, его размер буфера.</span><span class="sxs-lookup"><span data-stu-id="2a48a-245">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="2a48a-246">Включить B4004:When надежного обмена сообщениями потока управления, Источник надежного обмена сообщениями WCF использует значение `netrm:BufferRemaining` регулирования передачу сообщений.</span><span class="sxs-lookup"><span data-stu-id="2a48a-246">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="2a48a-247">B4005: WCF формирует `netrm:BufferRemaining` integer значения от 0 до 4096 включительно и считывает целые значения в диапазоне от 0 и `xs:int` `maxInclusive` значение 214748364 включительно.</span><span class="sxs-lookup"><span data-stu-id="2a48a-247">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="2a48a-248">Шаблоны обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="2a48a-248">Message Exchange Patterns</span></span>  
 <span data-ttu-id="2a48a-249">Этот раздел описывает поведение WCF, при использовании протокола WS-ReliableMessaging для различных шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2a48a-249">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="2a48a-250">Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:</span><span class="sxs-lookup"><span data-stu-id="2a48a-250">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="2a48a-251">неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;</span><span class="sxs-lookup"><span data-stu-id="2a48a-251">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="2a48a-252">адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-252">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="2a48a-253">Односторонний неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="2a48a-253">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2a48a-254">Привязка</span><span class="sxs-lookup"><span data-stu-id="2a48a-254">Binding</span></span>  
 <span data-ttu-id="2a48a-255">WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="2a48a-255">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="2a48a-256">WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="2a48a-256">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2a48a-257">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-258">Передает инициатора WCF `CreateSequence` сообщений которых не `Offer` элемент в HTTP-запросе и ожидает `CreateSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-258">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2a48a-259">Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений нет `Accept` элемент в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-259">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="2a48a-260">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="2a48a-260">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="2a48a-261">Инициатор WCF обрабатывает подтверждения при ответе на все сообщения, за исключением `CreateSequence` сообщений и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="2a48a-261">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="2a48a-262">Респондент WCF всегда передает отдельное подтверждение в HTTP-ответе на все последовательности и `AckRequested` сообщений.</span><span class="sxs-lookup"><span data-stu-id="2a48a-262">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="2a48a-263">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-263">CloseSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-264">Инициатор WCF передает `CloseSequence` сообщение HTTP-запроса и ожидает `CreateSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-264">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2a48a-265">Респондент WCF передает `CloseSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-265">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="2a48a-266">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-266">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-267">Инициатор WCF передает `TerminateSequence` сообщение HTTP-запроса и ожидает `TerminateSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-267">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2a48a-268">Респондент WCF передает `TerminateSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-268">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="2a48a-269">Односторонний адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="2a48a-269">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2a48a-270">Привязка</span><span class="sxs-lookup"><span data-stu-id="2a48a-270">Binding</span></span>  
 <span data-ttu-id="2a48a-271">WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="2a48a-271">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="2a48a-272">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="2a48a-272">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2a48a-273">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2a48a-273">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2a48a-274">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-274">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-275">Инициатор WCF передает `CreateSequence` сообщений нет `Offer` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="2a48a-275">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="2a48a-276">Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений нет `Accept` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="2a48a-276">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="2a48a-277">Дуплексный адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="2a48a-277">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2a48a-278">Привязка</span><span class="sxs-lookup"><span data-stu-id="2a48a-278">Binding</span></span>  
 <span data-ttu-id="2a48a-279">WCF предоставляет полностью асинхронного, двустороннего обмена сообщениями с использованием двух последовательностей через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="2a48a-279">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="2a48a-280">Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-280">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="2a48a-281">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="2a48a-281">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2a48a-282">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2a48a-282">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2a48a-283">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-283">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-284">Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="2a48a-284">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="2a48a-285">Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемента, после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемента.</span><span class="sxs-lookup"><span data-stu-id="2a48a-285">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="2a48a-286">Время существования последовательности</span><span class="sxs-lookup"><span data-stu-id="2a48a-286">Sequence Lifetime</span></span>  
 <span data-ttu-id="2a48a-287">WCF две последовательности рассматриваются в качестве одного полностью двустороннего сеанса.</span><span class="sxs-lookup"><span data-stu-id="2a48a-287">WCF treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="2a48a-288">При создании ошибки разрыва одной последовательности, WCF предполагает, что Удаленная конечная точка разрыв в обеих последовательностях.</span><span class="sxs-lookup"><span data-stu-id="2a48a-288">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="2a48a-289">После чтения разрыва одной последовательности, WCF ошибках обеих последовательностях.</span><span class="sxs-lookup"><span data-stu-id="2a48a-289">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="2a48a-290">WCF можно закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности.</span><span class="sxs-lookup"><span data-stu-id="2a48a-290">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="2a48a-291">И наоборот WCF может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.</span><span class="sxs-lookup"><span data-stu-id="2a48a-291">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="2a48a-292">Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="2a48a-292">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2a48a-293">Привязка</span><span class="sxs-lookup"><span data-stu-id="2a48a-293">Binding</span></span>  
 <span data-ttu-id="2a48a-294">WCF предоставляет одностороннее и шаблон обмена сообщениями запрос ответ, с использованием двух последовательностей через один канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="2a48a-294">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="2a48a-295">WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="2a48a-295">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2a48a-296">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-296">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-297">Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент в HTTP-запросе и ожидает `CreateSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-297">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="2a48a-298">Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-298">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="2a48a-299">Односторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="2a48a-299">One-way Message</span></span>  
 <span data-ttu-id="2a48a-300">Для успешного завершения односторонний обмен сообщениями WCF инициатора передает сообщение последовательности запросов в HTTP-запросе и получает отдельное `SequenceAcknowledgement` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-300">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="2a48a-301">Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="2a48a-301">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="2a48a-302">Респондент WCF может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2a48a-302">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="2a48a-303">Двусторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="2a48a-303">Two Way Messages</span></span>  
 <span data-ttu-id="2a48a-304">Для реализации протокола двустороннего сообщений exchange, инициатор WCF передает сообщение последовательности запросов в HTTP-запросе и получает сообщение последовательности ответов в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-304">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="2a48a-305">Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.</span><span class="sxs-lookup"><span data-stu-id="2a48a-305">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="2a48a-306">Респондент WCF может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2a48a-306">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="2a48a-307">Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.</span><span class="sxs-lookup"><span data-stu-id="2a48a-307">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="2a48a-308">Повторные попытки ответов</span><span class="sxs-lookup"><span data-stu-id="2a48a-308">Retrying Replies</span></span>  
 <span data-ttu-id="2a48a-309">WCF использует корреляцию запросов и ответов HTTP для корреляции протокола двустороннего сообщений exchange.</span><span class="sxs-lookup"><span data-stu-id="2a48a-309">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="2a48a-310">По этой причине инициатора WCF не прекращает попытки сообщение последовательности запросов, когда подтверждается сообщение последовательности запросов а дожидается HTTP-ответа, содержащего `SequenceAcknowledgement`, ответ приложения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="2a48a-310">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="2a48a-311">Респондент WCF повторяет ответы HTTP-ответе запроса, с которой связан этот ответ.</span><span class="sxs-lookup"><span data-stu-id="2a48a-311">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="2a48a-312">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-312">CloseSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-313">После получения всех сообщений последовательности ответов и подтверждений для всех сообщений последовательности одним из способов запроса, инициатором WCF передает `CloseSequence` сообщение последовательности запросов в HTTP-запросе и ожидает `CloseSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-313">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="2a48a-314">Закрытие последовательности запросов неявным образом закрывает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="2a48a-314">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="2a48a-315">Это означает, что инициатор WCF включает последнее подтверждение последовательности ответа `SequenceAcknowledgement` на `CloseSequence` сообщение и последовательности ответов нет `CloseSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="2a48a-315">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="2a48a-316">Респондент WCF обеспечивает все ответы подтверждения и передает `CloseSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-316">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="2a48a-317">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-317">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-318">После получения `CloseSequenceResponse` передает сообщения WCF инициатора `TerminateSequence` сообщение последовательности запросов в HTTP-запросе и ожидает `TerminateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-318">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="2a48a-319">Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="2a48a-319">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="2a48a-320">Это означает, что инициатор WCF включает последнее подтверждение последовательности ответа `SequenceAcknowledgement` на `TerminateSequence` сообщение и последовательности ответов нет `TerminateSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="2a48a-320">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="2a48a-321">Респондент WCF передает `TerminateSequenceResponse` сообщение HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="2a48a-321">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="2a48a-322">Обмен сообщениями запрос-ответ, адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="2a48a-322">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="2a48a-323">Привязка</span><span class="sxs-lookup"><span data-stu-id="2a48a-323">Binding</span></span>  
 <span data-ttu-id="2a48a-324">WCF предоставляет шаблон обмена сообщениями запрос ответ с использованием двух последовательностей через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="2a48a-324">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="2a48a-325">Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-325">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="2a48a-326">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="2a48a-326">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="2a48a-327">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="2a48a-327">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="2a48a-328">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="2a48a-328">CreateSequence Exchange</span></span>  
 <span data-ttu-id="2a48a-329">Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="2a48a-329">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="2a48a-330">Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемент после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемента.</span><span class="sxs-lookup"><span data-stu-id="2a48a-330">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="2a48a-331">Корреляция запросов и ответов</span><span class="sxs-lookup"><span data-stu-id="2a48a-331">Request/Reply Correlation</span></span>  
 <span data-ttu-id="2a48a-332">Следующие действия относятся ко всем связанным запросам и ответам.</span><span class="sxs-lookup"><span data-stu-id="2a48a-332">The following applies to all correlated requests and replies:</span></span>  
  
-   <span data-ttu-id="2a48a-333">WCF обеспечивает все сообщения запроса приложения содержат `ReplyTo` ссылки на конечную точку и `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-333">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   <span data-ttu-id="2a48a-334">WCF применяется ссылка локальную конечную точку каждого сообщения с запросом приложения `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-334">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="2a48a-335">Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.</span><span class="sxs-lookup"><span data-stu-id="2a48a-335">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   <span data-ttu-id="2a48a-336">WCF обеспечивает сообщения, входящих запросов содержали `MessageId` и `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="2a48a-336">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   <span data-ttu-id="2a48a-337">WCF обеспечивает `ReplyTo` URI конечной точки ссылки всех сообщений запросов приложения соответствует ссылке локальную конечную точку, как определено ранее.</span><span class="sxs-lookup"><span data-stu-id="2a48a-337">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   <span data-ttu-id="2a48a-338">WCF обеспечивает, что все ответы содержат правильные `RelatesTo` и `To` заголовки `wsa` правилам связывания запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="2a48a-338">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
