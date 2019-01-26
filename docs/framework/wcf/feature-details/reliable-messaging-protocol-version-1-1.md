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
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="e6847-102">Протокол надежного обмена сообщениями, версия 1,1</span><span class="sxs-lookup"><span data-stu-id="e6847-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="e6847-103">В этом разделе рассматриваются сведения о реализации Windows Communication Foundation (WCF) для WS-ReliableMessaging протокола февраля 2007 г. (версия 1.1), необходимые для взаимодействия с использованием транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6847-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="e6847-104">WCF соответствует спецификации WS-ReliableMessaging с определенными ограничениями и пояснениями, описанными далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e6847-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="e6847-105">Обратите внимание, что реализуется начиная с версии 1.1 протокола WS-ReliableMessaging [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6847-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="e6847-106">WS-ReliableMessaging февраля 2007 г. протокол реализуется в WCF, <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="e6847-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="e6847-107">Для удобства объяснения в этом разделе используются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="e6847-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="e6847-108">Инициатор: Клиент, инициирующий Создание последовательности сообщений WS-Reliable.</span><span class="sxs-lookup"><span data-stu-id="e6847-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="e6847-109">Респондент: Служба, получающая запросы инициатора.</span><span class="sxs-lookup"><span data-stu-id="e6847-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="e6847-110">В этом документе используются префиксы и пространства имен, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e6847-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="e6847-111">Префикс</span><span class="sxs-lookup"><span data-stu-id="e6847-111">Prefix</span></span>|<span data-ttu-id="e6847-112">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e6847-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="e6847-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="e6847-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|<span data-ttu-id="e6847-114">netrm</span><span class="sxs-lookup"><span data-stu-id="e6847-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|  
|<span data-ttu-id="e6847-115">s</span><span class="sxs-lookup"><span data-stu-id="e6847-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="e6847-116">wsa</span><span class="sxs-lookup"><span data-stu-id="e6847-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|<span data-ttu-id="e6847-117">wsse</span><span class="sxs-lookup"><span data-stu-id="e6847-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="e6847-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="e6847-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|<span data-ttu-id="e6847-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="e6847-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|<span data-ttu-id="e6847-120">wsp</span><span class="sxs-lookup"><span data-stu-id="e6847-120">wsp</span></span>|<span data-ttu-id="e6847-121">(WS-Policy 1.2 или WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="e6847-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="e6847-122">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="e6847-122">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="e6847-123">Создание последовательности</span><span class="sxs-lookup"><span data-stu-id="e6847-123">Sequence Creation</span></span>  
 <span data-ttu-id="e6847-124">В WCF реализована `CreateSequence` и `CreateSequenceResponse` последовательности сообщений для установления надежный обмен сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6847-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="e6847-125">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="e6847-125">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="e6847-126">B1101: Инициатор WCF использует одну и ту же ссылку конечной точки как `CreateSequence` сообщения `ReplyTo`, `AcksTo` и `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="e6847-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="e6847-127">R1102: `AcksTo`, `ReplyTo` И `Offer/Endpoint` ссылается на конечную точку в `CreateSequence` сообщения должны иметь значения адресов идентичные строковые представления, таким образом, чтобы они совпадали на уровне октетов.</span><span class="sxs-lookup"><span data-stu-id="e6847-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="e6847-128">Респондент WCF проверяет, что часть URI `AcksTo`, `ReplyTo` и `Endpoint` идентичны ссылки на конечные точки перед созданием последовательности.</span><span class="sxs-lookup"><span data-stu-id="e6847-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="e6847-129">R1103: `AcksTo`, `ReplyTo` И `Offer/Endpoint` ссылается на конечную точку в `CreateSequence` сообщения должны иметь тот же набор параметров ссылок.</span><span class="sxs-lookup"><span data-stu-id="e6847-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="e6847-130">WCF не применяет принудительно, но предполагается, что ссылочные параметры `AcksTo`, `ReplyTo` и `Offer/Endpoint` на конечные точки `CreateSequence` идентичны и используются параметры ссылки `ReplyTo` ссылки на конечную точку подтверждениях и сообщениях встречной последовательности.</span><span class="sxs-lookup"><span data-stu-id="e6847-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="e6847-131">B1104: Инициатор WCF не создает необязательный `Expires` или `Offer/Expires` элемент в `CreateSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="e6847-132">B1105: При доступе к `CreateSequence` сообщение, отвечающее устройство WCF использует `Expires` значение в `CreateSequence` элемент как `Expires` значение в `CreateSequenceResponse` элемент.</span><span class="sxs-lookup"><span data-stu-id="e6847-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="e6847-133">В противном случае респондент WCF считывает и игнорирует `Expires` и `Offer/Expires` значения.</span><span class="sxs-lookup"><span data-stu-id="e6847-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="e6847-134">B1106: При доступе к `CreateSequenceResponse` сообщение, инициатор WCF считывает необязательное `Expires` значение, но не использует его.</span><span class="sxs-lookup"><span data-stu-id="e6847-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="e6847-135">B1107: WCF-инициатор и отвечающее устройство всегда создают необязательный `IncompleteSequenceBehavior` элемент в `CreateSequence/Offer` и `CreateSequenceResponse` элементы.</span><span class="sxs-lookup"><span data-stu-id="e6847-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="e6847-136">B1108: WCF использует только `DiscardFollowingFirstGap` и `NoDiscard` значения в `IncompleteSequenceBehavior` элемент.</span><span class="sxs-lookup"><span data-stu-id="e6847-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="e6847-137">Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.</span><span class="sxs-lookup"><span data-stu-id="e6847-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="e6847-138">B1109: Если `CreateSequence` содержит `Offer` элемент, один из способов WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceResponse` без `Accept` элемент.</span><span class="sxs-lookup"><span data-stu-id="e6847-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="e6847-139">B1110: Если респондент отклоняет предложенную последовательность, инициатор WCF ошибки последовательность.</span><span class="sxs-lookup"><span data-stu-id="e6847-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="e6847-140">B1111: Если `CreateSequence` не содержит `Offer` элемент, двустороннее WCF респондент отклоняет предложенную последовательность, отправляя в ответ `CreateSequenceRefused` сбоя.</span><span class="sxs-lookup"><span data-stu-id="e6847-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="e6847-141">R1112: При установлении двух встречных последовательностей с помощью `Offer` механизм, `[address]` свойство `CreateSequenceResponse/Accept/AcksTo` ссылки на конечную точку должен соответствовать URI назначения из `CreateSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="e6847-142">R1113: При установлении двух встречных последовательностей с помощью `Offer` механизм, все сообщения в обеих последовательностях от инициатора к респонденту должны быть отправлены в одну и ту же ссылку конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e6847-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="e6847-143">WCF использует WS-ReliableMessaging для установки надежных сеансов между инициатором и респондентом.</span><span class="sxs-lookup"><span data-stu-id="e6847-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="e6847-144">Реализация WCF WS-ReliableMessaging обеспечивает создание надежного сеанса для односторонней связи, запрос ответ и полный двустороннего обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6847-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="e6847-145">Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6847-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="e6847-146">Так как WCF гарантирует безопасность таких сеансов, включая защиту end-to-end для обеспечения целостности сеанса, целесообразно убедиться, что сообщения, предназначенные для той же стороне прибывают в том же месте назначения.</span><span class="sxs-lookup"><span data-stu-id="e6847-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="e6847-147">Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений.</span><span class="sxs-lookup"><span data-stu-id="e6847-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="e6847-148">Таким образом R1102 R1112 и R1113 ограничения на платформу WCF.</span><span class="sxs-lookup"><span data-stu-id="e6847-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>  
  
 <span data-ttu-id="e6847-149">Пример сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="e6847-149">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="e6847-150">Пример сообщения `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="e6847-150">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="e6847-151">Закрытие последовательности</span><span class="sxs-lookup"><span data-stu-id="e6847-151">Closing a Sequence</span></span>  
 <span data-ttu-id="e6847-152">WCF использует `CloseSequence` и `CloseSequenceResponse` сообщения для завершения инициативе источника системы надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6847-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="e6847-153">Назначение надежного обмена сообщениями WCF не инициируют завершение работы и Источник надежного обмена сообщениями WCF не поддерживает завершение работы системы надежного обмена сообщениями инициируемое точкой назначения.</span><span class="sxs-lookup"><span data-stu-id="e6847-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="e6847-154">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="e6847-154">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="e6847-155">B1201: Источник надежного обмена сообщениями WCF всегда отправляет `CloseSequence` сообщения для закрытия последовательности.</span><span class="sxs-lookup"><span data-stu-id="e6847-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="e6847-156">B1202: Источник системы надежного обмена сообщениями ожидает подтверждения перед отправкой полного диапазона всех сообщений последовательности `CloseSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="e6847-157">B1203: Источник системы надежного обмена сообщениями всегда включает необязательный `LastMsgNumber` элемент, если последовательность не содержит сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="e6847-158">R1204: Назначения системы надежного обмена сообщениями не должна инициировать, отправляя `CloseSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="e6847-159">B1205: При получении сообщения `CloseSequence` сообщение, источнику надежного обмена сообщениями WCF считает, что последовательность неполными и отправляет ошибку.</span><span class="sxs-lookup"><span data-stu-id="e6847-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="e6847-160">Пример сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="e6847-160">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="e6847-161">Завершение последовательности</span><span class="sxs-lookup"><span data-stu-id="e6847-161">Sequence Termination</span></span>  
 <span data-ttu-id="e6847-162">WCF в основном используется `TerminateSequence/TerminateSequenceResponse` подтверждение, после завершения `CloseSequence/CloseSequenceResponse` подтверждения.</span><span class="sxs-lookup"><span data-stu-id="e6847-162">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="e6847-163">Назначение надежного обмена сообщениями WCF инициирует завершение последовательности, а источник системы надежного обмена сообщениями не поддерживает завершение инициируемое точкой назначения системы надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6847-163">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="e6847-164">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="e6847-164">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="e6847-165">B1301: Инициатор WCF отправляет только `TerminateSequence` сообщения после успешного завершения `CloseSequence/CloseSequenceResponse` подтверждения.</span><span class="sxs-lookup"><span data-stu-id="e6847-165">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="e6847-166">R1302: СРЕДА WCF проверяет, что `LastMsgNumber` элемента одинаков во всех `CloseSequence` и `TerminateSequence` сообщений для заданной последовательности.</span><span class="sxs-lookup"><span data-stu-id="e6847-166">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="e6847-167">Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="e6847-167">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="e6847-168">B1303: При получении `TerminateSequence` сообщения после `CloseSequence/CloseSequenceResponse` подтверждения назначения системы надежного обмена сообщениями отвечает `TerminateSequenceResponse` сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-168">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="e6847-169">Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.</span><span class="sxs-lookup"><span data-stu-id="e6847-169">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="e6847-170">B1304: При получении `TerminateSequence` сообщений до `CloseSequence/CloseSequenceResponse` подтверждения назначения надежного обмена сообщениями WCF отвечает `TerminateSequenceResponse` сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-170">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="e6847-171">Если точка назначения системы надежного обмена сообщениями определяет, что в последовательности нет противоречий, она, прежде чем высвободить ресурсы, ждет в течение времени, заданного точкой назначения приложения, чтобы клиент мог получить последнее подтверждение.</span><span class="sxs-lookup"><span data-stu-id="e6847-171">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="e6847-172">В противном случае точка назначения системы надежного обмена сообщениями сразу же высвобождает ресурсы и сообщает точке назначения приложения, что последовательность завершена, но не гарантированно, вызывая для этого событие `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="e6847-172">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="e6847-173">Пример сообщения `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="e6847-173">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="e6847-174">Последовательности</span><span class="sxs-lookup"><span data-stu-id="e6847-174">Sequences</span></span>  
 <span data-ttu-id="e6847-175">Ниже приведен список ограничений, относящихся к последовательностям.</span><span class="sxs-lookup"><span data-stu-id="e6847-175">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="e6847-176">Создает B1401:WCF и обращается к порядковые номера, не превышающие `xs:long`его максимального значения 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="e6847-176">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="e6847-177">Пример заголовка `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="e6847-177">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="e6847-178">Запрос подтверждения</span><span class="sxs-lookup"><span data-stu-id="e6847-178">Request Acknowledgement</span></span>  
 <span data-ttu-id="e6847-179">WCF использует `AckRequested` заголовок как механизм поддержания активности.</span><span class="sxs-lookup"><span data-stu-id="e6847-179">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="e6847-180">Пример заголовка `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="e6847-180">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="e6847-181">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="e6847-181">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="e6847-182">WCF использует «» подтверждений для подтверждений последовательностей в WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="e6847-182">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="e6847-183">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="e6847-183">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="e6847-184">R1601: При установлении двух встречных последовательностей с помощью `Offer` механизм, `SequenceAcknowledgement` заголовка может быть включено в любое сообщение приложения предполагаемому получателю.</span><span class="sxs-lookup"><span data-stu-id="e6847-184">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="e6847-185">Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="e6847-185">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="e6847-186">B1602: WCF не создает `SequenceAcknowledgement` заголовков, содержащих `Nack` элементов.</span><span class="sxs-lookup"><span data-stu-id="e6847-186">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="e6847-187">WCF проверяет, что каждый `Nack` элемент содержит порядковый номер, но в противном случае игнорирует `Nack` элемент и значение.</span><span class="sxs-lookup"><span data-stu-id="e6847-187">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="e6847-188">Пример заголовка `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="e6847-188">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="e6847-189">Ошибки протокола WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="e6847-189">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="e6847-190">Ниже приведен список ограничений, относящихся к реализации ошибок WS-ReliableMessaging WCF.</span><span class="sxs-lookup"><span data-stu-id="e6847-190">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="e6847-191">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="e6847-191">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="e6847-192">B1701: WCF не создает `MessageNumberRollover` ошибок.</span><span class="sxs-lookup"><span data-stu-id="e6847-192">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="e6847-193">B1702: Через SOAP 1.2, когда конечная точка службы достигает достигается максимальное число подключений и не может обработать новые подключения, WCF создает вложенный `CreateSequenceRefused` код ошибки, `netrm:ConnectionLimitReached`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e6847-193">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="e6847-194">Ошибки WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="e6847-194">WS-Addressing Faults</span></span>  
 <span data-ttu-id="e6847-195">Так как WS-ReliableMessaging использует WS-Addressing, реализация WCF WS-ReliableMessaging может создавать и передавать ошибки WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="e6847-195">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="e6847-196">В этом разделе описаны ошибки WS-Addressing, которые WCF явным образом создает и передает на уровне WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="e6847-196">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="e6847-197">B1801:WCF создает и передает `Message Addressing Header Required` сбоя при выполнении одного из следующих:</span><span class="sxs-lookup"><span data-stu-id="e6847-197">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="e6847-198">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;</span><span class="sxs-lookup"><span data-stu-id="e6847-198">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="e6847-199">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;</span><span class="sxs-lookup"><span data-stu-id="e6847-199">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="e6847-200">в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="e6847-200">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="e6847-201">B1802:WCF создает и передает `Endpoint Unavailable` сбоя для указания нет конечной точки прослушивания, который может обработать последовательность на основании проверки заголовков адресов в `CreateSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-201">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="e6847-202">Сочетаемость протокола</span><span class="sxs-lookup"><span data-stu-id="e6847-202">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="e6847-203">Сочетаемость с WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="e6847-203">Composition with WS-Addressing</span></span>  
 <span data-ttu-id="e6847-204">WCF поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и W3C WS-Addressing 1.0 рекомендации [WS-ADDR-CORE] и [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="e6847-204">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="e6847-205">Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="e6847-205">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="e6847-206">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="e6847-206">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="e6847-207">R2101: С помощью WS-Reliable Messaging можно использовать как WS-Addressing 2004/08, так и WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="e6847-207">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="e6847-208">R2102: Следует использовать одну версию WS-Addressing заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью `Offer` механизм.</span><span class="sxs-lookup"><span data-stu-id="e6847-208">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="e6847-209">Сочетаемость с SOAP</span><span class="sxs-lookup"><span data-stu-id="e6847-209">Composition with SOAP</span></span>  
 <span data-ttu-id="e6847-210">WCF поддерживает использование протокола SOAP 1.1 и SOAP 1.2 с WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="e6847-210">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="e6847-211">Сочетаемость с WS-Security и WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="e6847-211">Composition with WS-Security and WS-SecureConversation</span></span>  
 <span data-ttu-id="e6847-212">WCF обеспечивает защиту последовательностей WS-ReliableMessaging с помощью безопасного транспорта (HTTPS), сочетаемость с WS-Security и WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="e6847-212">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="e6847-213">Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="e6847-213">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="e6847-214">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="e6847-214">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="e6847-215">R2301: Для защиты целостности последовательности WS-ReliableMessaging в дополнение к целостности и конфиденциальности отдельных сообщений, WCF требует, что необходимо использовать WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="e6847-215">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="e6847-216">R2302:AWS-Secure Conversation должен быть установлен сеанс WS-ReliableMessaging перед установкой последовательностей.</span><span class="sxs-lookup"><span data-stu-id="e6847-216">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="e6847-217">R2303: Если время существования последовательности WS-ReliableMessaging существования сеанса WS-Secure Conversation, превышает `SecurityContextToken` установить с помощью WS-Secure Conversation должен обновляться с помощью привязки обновления WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="e6847-217">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="e6847-218">B2304:ws-последовательность ReliableMessaging или пара встречных последовательностей всегда ограничены одним сеансом WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="e6847-218">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="e6847-219">R2305: При использовании с WS-Secure Conversation, отвечающая сторона WCF требует, `CreateSequence` сообщение содержит `wsse:SecurityTokenReference` элемент и `wsrm:UsesSequenceSTR` заголовка.</span><span class="sxs-lookup"><span data-stu-id="e6847-219">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="e6847-220">Пример заголовка `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="e6847-220">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="e6847-221">Сочетаемость с сеансами SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="e6847-221">Composition with SSL/TLS sessions</span></span>  
 <span data-ttu-id="e6847-222">WCF не поддерживает совместное использование с сеансами SSL/TLS:</span><span class="sxs-lookup"><span data-stu-id="e6847-222">WCF does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="e6847-223">B2401: WCF не создает `wsrm:UsesSequenceSSL` заголовка.</span><span class="sxs-lookup"><span data-stu-id="e6847-223">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="e6847-224">R2402: Надежного обмена сообщениями инициатор не должен отправлять `CreateSequence` сообщений с `wsrm:UsesSequenceSSL` заголовок, чтобы респондент WCF.</span><span class="sxs-lookup"><span data-stu-id="e6847-224">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="e6847-225">Сочетаемость с WS-Policy</span><span class="sxs-lookup"><span data-stu-id="e6847-225">Composition with WS-Policy</span></span>  
 <span data-ttu-id="e6847-226">WCF поддерживает две версии WS-Policy: WS-Policy 1.2 и WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="e6847-226">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="e6847-227">Утверждение WS-ReliableMessaging WS-Policy</span><span class="sxs-lookup"><span data-stu-id="e6847-227">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="e6847-228">WCF использует утверждение WS-Policy WS-ReliableMessaging `wsrm:RMAssertion` для описания возможностей конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e6847-228">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="e6847-229">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="e6847-229">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="e6847-230">B3001: WCF присоединяет `wsrmn:RMAssertion` утверждение WS-Policy для `wsdl:binding` элементов.</span><span class="sxs-lookup"><span data-stu-id="e6847-230">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="e6847-231">WCF поддерживает вложения в `wsdl:binding` и `wsdl:port` элементы.</span><span class="sxs-lookup"><span data-stu-id="e6847-231">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="e6847-232">B3002: WCF никогда не создает `wsp:Optional` тега.</span><span class="sxs-lookup"><span data-stu-id="e6847-232">B3002: WCF never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="e6847-233">B3003: При доступе к `wsrmp:RMAssertion` утверждение WS-Policy, WCF игнорирует `wsp:Optional` тегов и считает политики WS-RM обязательным.</span><span class="sxs-lookup"><span data-stu-id="e6847-233">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="e6847-234">R3004: Поскольку WCF не используются совместно с сеансами SSL/TLS, WCF не принимает политика, задающая `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="e6847-234">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="e6847-235">B3005: WCF всегда создает `wsrmp:DeliveryAssurance` элемент.</span><span class="sxs-lookup"><span data-stu-id="e6847-235">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="e6847-236">B3006: WCF всегда указывает `wsrmp:ExactlyOnce` гарантии доставки.</span><span class="sxs-lookup"><span data-stu-id="e6847-236">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="e6847-237">B3007: WCF создает и считывает следующие свойства утверждения WS-ReliableMessaging и предоставляет контроль над ними на WCF`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="e6847-237">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="e6847-238">Пример `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="e6847-238">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="e6847-239">Расширение WS-ReliableMessaging для управления потоком</span><span class="sxs-lookup"><span data-stu-id="e6847-239">Flow Control WS-ReliableMessaging Extension</span></span>  
 <span data-ttu-id="e6847-240">WCF использует расширяемость WS-ReliableMessaging, чтобы обеспечить необязательно более строгий контроль над потоком последовательности сообщений.</span><span class="sxs-lookup"><span data-stu-id="e6847-240">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="e6847-241">Управление потоком можно включить, задав <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="e6847-241">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="e6847-242">Ниже приведен список ограничений, относящихся к WCF:</span><span class="sxs-lookup"><span data-stu-id="e6847-242">The following is a list of constraints that apply to WCF:</span></span>  
  
-   <span data-ttu-id="e6847-243">B4001: При включении надежного обмена сообщениями потока управления, WCF создает `netrm:BufferRemaining` элемент расширения элемента `SequenceAcknowledgement` заголовка, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e6847-243">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="e6847-244">B4002: Даже при включении надежного обмена сообщениями потока управления WCF не требует `netrm:BufferRemaining` элемент `SequenceAcknowledgement` заголовка.</span><span class="sxs-lookup"><span data-stu-id="e6847-244">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="e6847-245">B4003: Назначение надежного обмена сообщениями WCF использует `netrm:BufferRemaining` для указания того, сколько новых сообщений его размер буфера.</span><span class="sxs-lookup"><span data-stu-id="e6847-245">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="e6847-246">Включен B4004:When надежного обмена сообщениями потока управления, Источник надежного обмена сообщениями WCF использует значение `netrm:BufferRemaining` для передачи сообщений.</span><span class="sxs-lookup"><span data-stu-id="e6847-246">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="e6847-247">B4005: WCF создает `netrm:BufferRemaining` целое число значений в диапазоне от 0 до 4096 включительно и считывает целые значения между 0 и `xs:int`в `maxInclusive` значение 214748364 включительно.</span><span class="sxs-lookup"><span data-stu-id="e6847-247">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="e6847-248">Шаблоны обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="e6847-248">Message Exchange Patterns</span></span>  
 <span data-ttu-id="e6847-249">В этом разделе описывает поведение WCF, когда WS-ReliableMessaging используется для различных шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e6847-249">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="e6847-250">Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:</span><span class="sxs-lookup"><span data-stu-id="e6847-250">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="e6847-251">Неадресуемый инициатор Инициатор расположен за брандмауэром; Респондент может отправлять сообщения инициатору только с HTTP-ответами.</span><span class="sxs-lookup"><span data-stu-id="e6847-251">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="e6847-252">Адресуемый инициатор Инициатор и отвечающее устройство можно отправлять HTTP-запросов; Другими словами можно установить два встречных HTTP-подключения.</span><span class="sxs-lookup"><span data-stu-id="e6847-252">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="e6847-253">Односторонний неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="e6847-253">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="e6847-254">Привязка</span><span class="sxs-lookup"><span data-stu-id="e6847-254">Binding</span></span>  
 <span data-ttu-id="e6847-255">WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6847-255">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="e6847-256">WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="e6847-256">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="e6847-257">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="e6847-258">Инициатор WCF передает `CreateSequence` сообщение, не имеющий `Offer` элемент HTTP-запрос и ожидает, что `CreateSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-258">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e6847-259">Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщение, не имеющий `Accept` элемент на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-259">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="e6847-260">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="e6847-260">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="e6847-261">Инициатор WCF обрабатывает подтверждения при ответе на все сообщения, за исключением `CreateSequence` сообщений и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e6847-261">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="e6847-262">Респондент WCF всегда передает отдельное подтверждение в HTTP-ответов все последовательности и `AckRequested` сообщений.</span><span class="sxs-lookup"><span data-stu-id="e6847-262">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="e6847-263">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-263">CloseSequence Exchange</span></span>  
 <span data-ttu-id="e6847-264">Инициатор WCF передает `CloseSequence` сообщений HTTP-запрос и ожидает, что `CreateSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-264">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e6847-265">Респондент WCF передает `CloseSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-265">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="e6847-266">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-266">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="e6847-267">Инициатор WCF передает `TerminateSequence` сообщений HTTP-запрос и ожидает, что `TerminateSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-267">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e6847-268">Респондент WCF передает `TerminateSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-268">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="e6847-269">Односторонний адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="e6847-269">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="e6847-270">Привязка</span><span class="sxs-lookup"><span data-stu-id="e6847-270">Binding</span></span>  
 <span data-ttu-id="e6847-271">WCF предоставляет шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6847-271">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="e6847-272">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="e6847-272">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="e6847-273">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e6847-273">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="e6847-274">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-274">CreateSequence Exchange</span></span>  
 <span data-ttu-id="e6847-275">Инициатор WCF передает `CreateSequence` сообщение, не имеющий `Offer` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="e6847-275">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="e6847-276">Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщение, не имеющий `Accept` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="e6847-276">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="e6847-277">Дуплексный адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="e6847-277">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="e6847-278">Привязка</span><span class="sxs-lookup"><span data-stu-id="e6847-278">Binding</span></span>  
 <span data-ttu-id="e6847-279">WCF предоставляет полностью асинхронные, двустороннего обмена сообщениями с использованием двух последовательностей через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6847-279">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="e6847-280">Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`.</span><span class="sxs-lookup"><span data-stu-id="e6847-280">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="e6847-281">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="e6847-281">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="e6847-282">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e6847-282">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="e6847-283">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-283">CreateSequence Exchange</span></span>  
 <span data-ttu-id="e6847-284">Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="e6847-284">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="e6847-285">Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемент, после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент.</span><span class="sxs-lookup"><span data-stu-id="e6847-285">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="e6847-286">Время существования последовательности</span><span class="sxs-lookup"><span data-stu-id="e6847-286">Sequence Lifetime</span></span>  
 <span data-ttu-id="e6847-287">WCF две последовательности рассматриваются в качестве одного полностью двустороннего сеанса.</span><span class="sxs-lookup"><span data-stu-id="e6847-287">WCF treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="e6847-288">После создания разрыва одной последовательности, WCF предполагает, что Удаленная конечная точка сбой обоих последовательностей.</span><span class="sxs-lookup"><span data-stu-id="e6847-288">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="e6847-289">После чтения разрыва в одной последовательности, WCF создает ошибки обоих последовательностей.</span><span class="sxs-lookup"><span data-stu-id="e6847-289">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>  
  
 <span data-ttu-id="e6847-290">WCF можно закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности.</span><span class="sxs-lookup"><span data-stu-id="e6847-290">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="e6847-291">И наоборот WCF может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.</span><span class="sxs-lookup"><span data-stu-id="e6847-291">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="e6847-292">Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="e6847-292">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="e6847-293">Привязка</span><span class="sxs-lookup"><span data-stu-id="e6847-293">Binding</span></span>  
 <span data-ttu-id="e6847-294">WCF предоставляет одностороннее и шаблон обмена сообщениями типа запрос ответ, с использованием двух последовательностей через один канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6847-294">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="e6847-295">WCF использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="e6847-295">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="e6847-296">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-296">CreateSequence Exchange</span></span>  
 <span data-ttu-id="e6847-297">Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запрос и ожидает, что `CreateSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-297">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="e6847-298">Респондент WCF создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-298">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="e6847-299">Односторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="e6847-299">One-way Message</span></span>  
 <span data-ttu-id="e6847-300">Чтобы успешно завершить односторонний обмен сообщениями, инициатор WCF передает сообщение последовательности запросов в HTTP-запрос и получает отдельное `SequenceAcknowledgement` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-300">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="e6847-301">Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="e6847-301">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="e6847-302">Респондент WCF может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e6847-302">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="e6847-303">Двусторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="e6847-303">Two Way Messages</span></span>  
 <span data-ttu-id="e6847-304">Для реализации протокола двустороннего сообщений exchange, инициатор WCF передает сообщение последовательности запросов в HTTP-запрос и получает сообщение последовательности ответов на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-304">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="e6847-305">Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.</span><span class="sxs-lookup"><span data-stu-id="e6847-305">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="e6847-306">Респондент WCF может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e6847-306">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="e6847-307">Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.</span><span class="sxs-lookup"><span data-stu-id="e6847-307">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="e6847-308">Повторные попытки ответов</span><span class="sxs-lookup"><span data-stu-id="e6847-308">Retrying Replies</span></span>  
 <span data-ttu-id="e6847-309">WCF использует корреляцию запросов и ответов HTTP для корреляции протокола двустороннего обмена.</span><span class="sxs-lookup"><span data-stu-id="e6847-309">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="e6847-310">По этой причине инициатора WCF не прекращает попытки отправки сообщение последовательности запросов, когда подтверждается сообщение последовательности запросов, но вместо этого при HTTP-ответа содержит `SequenceAcknowledgement`, ответ приложения или сбоя.</span><span class="sxs-lookup"><span data-stu-id="e6847-310">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="e6847-311">Респондент WCF повторяет ответы на HTTP-ответа запроса, к которому связан этот ответ.</span><span class="sxs-lookup"><span data-stu-id="e6847-311">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="e6847-312">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-312">CloseSequence Exchange</span></span>  
 <span data-ttu-id="e6847-313">После получения всех сообщений последовательности ответов и подтверждений для всех сообщений последовательности односторонний запрос, инициатор WCF передает `CloseSequence` сообщений для последовательности запросов в HTTP-запросе и ожидает, что `CloseSequenceResponse` на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-313">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="e6847-314">Закрытие последовательности запросов неявным образом закрывает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="e6847-314">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="e6847-315">Это означает, что инициатор WCF включает последнее подтверждение последовательности ответов `SequenceAcknowledgement` на `CloseSequence` сообщения и последовательности ответов нет `CloseSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="e6847-315">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="e6847-316">Респондент WCF все ответы и подтверждения ранее и передает `CloseSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-316">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="e6847-317">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-317">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="e6847-318">После получения `CloseSequenceResponse` передает сообщение, инициатор WCF `TerminateSequence` сообщений для последовательности запросов в HTTP-запросе и ожидает, что `TerminateSequenceResponse` на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-318">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="e6847-319">Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="e6847-319">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="e6847-320">Это означает, что инициатор WCF включает последнее подтверждение последовательности ответов `SequenceAcknowledgement` на `TerminateSequence` сообщения и последовательности ответов нет `TerminateSequence` exchange.</span><span class="sxs-lookup"><span data-stu-id="e6847-320">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="e6847-321">Респондент WCF передает `TerminateSequenceResponse` сообщение на HTTP-ответа.</span><span class="sxs-lookup"><span data-stu-id="e6847-321">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="e6847-322">Обмен сообщениями запрос-ответ, адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="e6847-322">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="e6847-323">Привязка</span><span class="sxs-lookup"><span data-stu-id="e6847-323">Binding</span></span>  
 <span data-ttu-id="e6847-324">WCF предоставляет шаблон обмена сообщениями типа запрос ответ с использованием двух последовательностей через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="e6847-324">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="e6847-325">Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`.</span><span class="sxs-lookup"><span data-stu-id="e6847-325">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="e6847-326">WCF использует HTTP-запросы для передачи всех сообщений.</span><span class="sxs-lookup"><span data-stu-id="e6847-326">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="e6847-327">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="e6847-327">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="e6847-328">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="e6847-328">CreateSequence Exchange</span></span>  
 <span data-ttu-id="e6847-329">Инициатор WCF передает `CreateSequence` сообщений с `Offer` элемент HTTP-запроса.</span><span class="sxs-lookup"><span data-stu-id="e6847-329">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="e6847-330">Респондент WCF гарантирует, что `CreateSequence` имеет `Offer` элемент после чего создает последовательность и передает `CreateSequenceResponse` сообщений с `Accept` элемент.</span><span class="sxs-lookup"><span data-stu-id="e6847-330">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="e6847-331">Корреляция запросов и ответов</span><span class="sxs-lookup"><span data-stu-id="e6847-331">Request/Reply Correlation</span></span>  
 <span data-ttu-id="e6847-332">Следующие действия относятся ко всем связанным запросам и ответам.</span><span class="sxs-lookup"><span data-stu-id="e6847-332">The following applies to all correlated requests and replies:</span></span>  
  
-   <span data-ttu-id="e6847-333">WCF обеспечивает все сообщения запроса приложения содержат `ReplyTo` ссылки на конечную точку и `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="e6847-333">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   <span data-ttu-id="e6847-334">WCF применяет ссылку на локальную конечную точку как каждого сообщения с запросом приложения `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="e6847-334">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="e6847-335">Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.</span><span class="sxs-lookup"><span data-stu-id="e6847-335">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   <span data-ttu-id="e6847-336">WCF обеспечивает все сообщения этой входящих запросов содержат `MessageId` и `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="e6847-336">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   <span data-ttu-id="e6847-337">WCF обеспечивает `ReplyTo` URI ссылки на конечную точку из всех сообщений запросов приложения соответствует ссылки локальной конечной точки, как было описано ранее.</span><span class="sxs-lookup"><span data-stu-id="e6847-337">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   <span data-ttu-id="e6847-338">WCF гарантирует, что все ответы содержат правильные `RelatesTo` и `To` заголовки `wsa` правилам связывания запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="e6847-338">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
