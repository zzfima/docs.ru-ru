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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67df8b539109d7e4dafcbc42ad7679643767021a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="429a6-102">Протокол надежного обмена сообщениями, версия 1,1</span><span class="sxs-lookup"><span data-stu-id="429a6-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="429a6-103">В этом разделе описаны особенности реализации в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] протокола WS-ReliableMessaging (версия 1.1 от февраля 2007 года), необходимого для взаимодействия с использованием транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="429a6-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="429a6-104">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] соблюдена спецификация WS-ReliableMessaging с определенными ограничениями и пояснениями, описанными далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="429a6-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="429a6-105">Обратите внимание, что реализуется начиная с версии 1.1 протокола WS-ReliableMessaging [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="429a6-106">Версия протокола WS-ReliableMessaging от февраля 2007 г. реализована в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью класса <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="429a6-106">The WS-ReliableMessaging February 2007 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="429a6-107">Для удобства объяснения в этом разделе используются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="429a6-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="429a6-108">инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;</span><span class="sxs-lookup"><span data-stu-id="429a6-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="429a6-109">респондент: служба, получающая запросы инициатора.</span><span class="sxs-lookup"><span data-stu-id="429a6-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="429a6-110">В этом документе используются префиксы и пространства имен, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="429a6-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="429a6-111">Префикс</span><span class="sxs-lookup"><span data-stu-id="429a6-111">Prefix</span></span>|<span data-ttu-id="429a6-112">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="429a6-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="429a6-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="429a6-113">wsrm</span></span>|<span data-ttu-id="429a6-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span><span class="sxs-lookup"><span data-stu-id="429a6-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span></span>|  
|<span data-ttu-id="429a6-115">netrm</span><span class="sxs-lookup"><span data-stu-id="429a6-115">netrm</span></span>|<span data-ttu-id="429a6-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="429a6-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="429a6-117">s</span><span class="sxs-lookup"><span data-stu-id="429a6-117">s</span></span>|<span data-ttu-id="429a6-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="429a6-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="429a6-119">wsa</span><span class="sxs-lookup"><span data-stu-id="429a6-119">wsa</span></span>|<span data-ttu-id="429a6-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="429a6-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="429a6-121">wsse</span><span class="sxs-lookup"><span data-stu-id="429a6-121">wsse</span></span>|<span data-ttu-id="429a6-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="429a6-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="429a6-123">wsrmp</span><span class="sxs-lookup"><span data-stu-id="429a6-123">wsrmp</span></span>|<span data-ttu-id="429a6-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="429a6-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="429a6-125">netrmp</span><span class="sxs-lookup"><span data-stu-id="429a6-125">netrmp</span></span>|<span data-ttu-id="429a6-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="429a6-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="429a6-127">wsp</span><span class="sxs-lookup"><span data-stu-id="429a6-127">wsp</span></span>|<span data-ttu-id="429a6-128">(WS-Policy 1.2 или WS-Policy 1.5)</span><span class="sxs-lookup"><span data-stu-id="429a6-128">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="429a6-129">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="429a6-129">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="429a6-130">Создание последовательности</span><span class="sxs-lookup"><span data-stu-id="429a6-130">Sequence Creation</span></span>  
 <span data-ttu-id="429a6-131">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализованы сообщения `CreateSequence` и `CreateSequenceResponse`, позволяющие установить последовательность системы надежного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="429a6-131">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="429a6-132">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="429a6-132">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="429a6-133">B1101: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует одну и ту же ссылку в качестве конечных точек `CreateSequence`, `ReplyTo` и `AcksTo` в сообщении `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="429a6-133">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="429a6-134">R1102: адреса ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь идентичные строковые представления, чтобы они совпадали на уровне октетов.</span><span class="sxs-lookup"><span data-stu-id="429a6-134">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="429a6-135">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] перед созданием последовательности проверяет, что фрагменты ссылок на конечные точки `AcksTo`, `ReplyTo` и `Endpoint`, обозначающие универсальный код ресурса (URI), совпадают.</span><span class="sxs-lookup"><span data-stu-id="429a6-135">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="429a6-136">R1103: ссылки на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.</span><span class="sxs-lookup"><span data-stu-id="429a6-136">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   <span data-ttu-id="429a6-137">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предполагается, что параметры ссылок на конечные точки `AcksTo`, `ReplyTo` и `Offer/Endpoint` в сообщении `CreateSequence` совпадают, поэтому в подтверждениях и сообщениях встречной последовательности используются параметры ссылки на конечную точку `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="429a6-137">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="429a6-138">B1104: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создает необязательный элемент `Expires` или `Offer/Expires` в сообщении `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-138">B1104: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="429a6-139">B1105: при обращении к сообщению `CreateSequence` респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует значение `Expires` в элементе `CreateSequence` в качестве значения `Expires` в элементе `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-139">B1105: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="429a6-140">В противном случае респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] считывает и игнорирует значения `Expires` и `Offer/Expires`.</span><span class="sxs-lookup"><span data-stu-id="429a6-140">Otherwise, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="429a6-141">B1106: при обращении к сообщению `CreateSequenceResponse` инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] считывает необязательное значение `Expires`, но не использует его.</span><span class="sxs-lookup"><span data-stu-id="429a6-141">B1106: When accessing the `CreateSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="429a6-142">B1107: инициатор и респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создают необязательный элемент `IncompleteSequenceBehavior` в элементах `CreateSequence/Offer` и `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-142">B1107: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="429a6-143">B1108: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в элементе `DiscardFollowingFirstGap` используются только значения `NoDiscard` и `IncompleteSequenceBehavior`.</span><span class="sxs-lookup"><span data-stu-id="429a6-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="429a6-144">Протокол WS-ReliableMessaging использует механизм `Offer` для формирования двух связанных встречных последовательностей, которые составляют сеанс.</span><span class="sxs-lookup"><span data-stu-id="429a6-144">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="429a6-145">B1109: если сообщение `CreateSequence` содержит элемент `Offer`, то односторонний респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отклоняет предложенную последовательность, отправляя в ответ сообщение `CreateSequenceResponse` без элемента `Accept`.</span><span class="sxs-lookup"><span data-stu-id="429a6-145">B1109: If `CreateSequence` contains an `Offer` element, the one way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="429a6-146">B1110: если респондент отклоняет предложенную последовательность, инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] прерывает созданную последовательность.</span><span class="sxs-lookup"><span data-stu-id="429a6-146">B1110: If a Reliable Messaging Responder rejects the offered sequence, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="429a6-147">B1111: если сообщение `CreateSequence` не содержит элемент `Offer`, двусторонний респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отклоняет предложенную последовательность, отправляя в ответ ошибку `CreateSequenceRefused`.</span><span class="sxs-lookup"><span data-stu-id="429a6-147">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="429a6-148">R1112: при установке с помощью механизма `Offer` двух встречных последовательностей, свойство `[address]` ссылки на конечную точку `CreateSequenceResponse/Accept/AcksTo` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-148">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="429a6-149">R1113: при установке с помощью механизма `Offer` двух встречных последовательностей, все сообщения от инициатора к респонденту в обеих последовательностях должны отправляться по одной и той же ссылке на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="429a6-149">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 <span data-ttu-id="429a6-150">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] протокол WS-ReliableMessaging используется для установки надежных сеансов между инициатором и респондентом.</span><span class="sxs-lookup"><span data-stu-id="429a6-150">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="429a6-151">Реализация протокола WS-ReliableMessaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает создание надежного сеанса для односторонней связи, обмена запросами и ответами и для полностью двустороннего обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="429a6-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="429a6-152">Механизм `Offer` в сообщениях `CreateSequence` и `CreateSequenceResponse` протокола WS-ReliableMessaging позволяет устанавливать две связанные встречные последовательности и обеспечивает протокол сеанса, который можно использовать во всех конечных точках обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="429a6-152">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="429a6-153">Поскольку платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] гарантирует безопасность таких сеансов, включая сквозную защиту для обеспечения целостности сеанса, она позволяет проверять, что сообщения, предназначенные одной и той же стороне, достигнут одной и той же точки назначения.</span><span class="sxs-lookup"><span data-stu-id="429a6-153">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="429a6-154">Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений.</span><span class="sxs-lookup"><span data-stu-id="429a6-154">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="429a6-155">Таким образом, применяются ограничения R1102, R1112 и R1113 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-155">Therefore, constraints R1102, R1112, and R1113 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="429a6-156">Пример сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-156">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="429a6-157">Пример сообщения `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-157">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="closing-a-sequence"></a><span data-ttu-id="429a6-158">Закрытие последовательности</span><span class="sxs-lookup"><span data-stu-id="429a6-158">Closing a Sequence</span></span>  
 <span data-ttu-id="429a6-159">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для закрытия последовательности системы надежного обмена сообщениями по инициативе источника используются сообщения `CloseSequence` и `CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-159">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="429a6-160">Точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не инициирует закрытие сеанса, а источник системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает закрытие последовательности, инициируемое точкой назначения.</span><span class="sxs-lookup"><span data-stu-id="429a6-160">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate shutdown and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="429a6-161">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="429a6-161">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="429a6-162">B1201: источник системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для закрытия последовательности всегда отправляет сообщение `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-162">B1201: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="429a6-163">B1202: источник системы надежного обмена сообщениями перед отправкой сообщения `CloseSequence` ждет подтверждения от всех сообщений последовательности.</span><span class="sxs-lookup"><span data-stu-id="429a6-163">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="429a6-164">B1203: источник системы надежного обмена сообщениями всегда включает необязательный элемент `LastMsgNumber`, если в последовательности есть хотя бы одно сообщение.</span><span class="sxs-lookup"><span data-stu-id="429a6-164">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="429a6-165">R1204: точка назначения системы надежного обмена сообщениями не должна инициировать закрытие последовательности путем отправки сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-165">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="429a6-166">B1205: после получения сообщения `CloseSequence` источник системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] полагает, что последовательность не завершена, и отправляет ошибку.</span><span class="sxs-lookup"><span data-stu-id="429a6-166">B1205: Upon receiving a `CloseSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="429a6-167">Пример сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-167">An example of a `CloseSequence` message.</span></span>  
  
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
  
### <a name="sequence-termination"></a><span data-ttu-id="429a6-168">Завершение последовательности</span><span class="sxs-lookup"><span data-stu-id="429a6-168">Sequence Termination</span></span>  
 <span data-ttu-id="429a6-169">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] после подтверждения `TerminateSequence/TerminateSequenceResponse` в первую очередь используется подтверждение `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-169">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="429a6-170">Точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не инициирует завершение последовательности, а источник системы надежного обмена сообщениями не поддерживает завершение последовательности, инициируемое точкой назначения.</span><span class="sxs-lookup"><span data-stu-id="429a6-170">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="429a6-171">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="429a6-171">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="429a6-172">B1301: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет сообщение `TerminateSequence` только после успешного подтверждения `CloseSequence/CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-172">B1301: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="429a6-173">R1302: среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что элемент `LastMsgNumber` одинаков для всех сообщений `CloseSequence` и `TerminateSequence` в заданной последовательности.</span><span class="sxs-lookup"><span data-stu-id="429a6-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="429a6-174">Это значит, что значения `LastMsgNumber` либо отсутствуют во всех сообщениях `CloseSequence` и `TerminateSequence`, либо присутствуют и идентичны во всех сообщениях `CloseSequence` и `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-174">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="429a6-175">B1303: при получении сообщения `TerminateSequence` после подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями отправляет в ответ сообщение `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-175">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="429a6-176">Поскольку перед отправкой сообщения `TerminateSequence` у источника системы надежного обмена сообщениями имеется последнее подтверждение, точка назначения системы надежного обмена сообщениями точно знает, что последовательность завершается, и немедленно высвобождает ресурсы.</span><span class="sxs-lookup"><span data-stu-id="429a6-176">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="429a6-177">B1304: при получении сообщения `TerminateSequence` до подтверждения `CloseSequence/CloseSequenceResponse` точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отправляет в ответ сообщение `TerminateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-177">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="429a6-178">Если точка назначения системы надежного обмена сообщениями определяет, что в последовательности нет противоречий, она, прежде чем высвободить ресурсы, ждет в течение времени, заданного точкой назначения приложения, чтобы клиент мог получить последнее подтверждение.</span><span class="sxs-lookup"><span data-stu-id="429a6-178">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="429a6-179">В противном случае точка назначения системы надежного обмена сообщениями сразу же высвобождает ресурсы и сообщает точке назначения приложения, что последовательность завершена, но не гарантированно, вызывая для этого событие `Faulted`.</span><span class="sxs-lookup"><span data-stu-id="429a6-179">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="429a6-180">Пример сообщения `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-180">An example of a `TerminateSequence` message.</span></span>  
  
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
  
### <a name="sequences"></a><span data-ttu-id="429a6-181">Последовательности</span><span class="sxs-lookup"><span data-stu-id="429a6-181">Sequences</span></span>  
 <span data-ttu-id="429a6-182">Ниже приведен список ограничений, относящихся к последовательностям.</span><span class="sxs-lookup"><span data-stu-id="429a6-182">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="429a6-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к возникновению ошибки и обращается к порядковые номера не выше, чем `xs:long`максимальное значение включительно, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="429a6-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="429a6-184">Пример заголовка `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-184">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="429a6-185">Запрос подтверждения</span><span class="sxs-lookup"><span data-stu-id="429a6-185">Request Acknowledgement</span></span>  
 <span data-ttu-id="429a6-186">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в качестве механизма поддержки активности используется заголовок `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="429a6-186">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="429a6-187">Пример заголовка `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="429a6-187">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="429a6-188">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="429a6-188">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="429a6-189">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для передачи подтверждений последовательностей протокола WS-ReliableMessaging используются сообщения приложений.</span><span class="sxs-lookup"><span data-stu-id="429a6-189">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="429a6-190">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="429a6-190">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="429a6-191">R1601: При установке двух встречных последовательностей, устанавливаются с помощью `Offer` механизм, `SequenceAcknowledgement` заголовок может быть включено в любое сообщение приложения, передаваемых предполагаемому получателю.</span><span class="sxs-lookup"><span data-stu-id="429a6-191">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="429a6-192">Удаленная конечная точка должна иметь возможность получения доступа к передаваемому таким образом заголовку `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="429a6-192">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="429a6-193">B1602: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются заголовки `SequenceAcknowledgement`, содержащие элементы `Nack`.</span><span class="sxs-lookup"><span data-stu-id="429a6-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-194"> проверяет, содержит ли каждый элемент `Nack` номер последовательности, если нет, то элемент `Nack` и его значение пропускаются.</span><span class="sxs-lookup"><span data-stu-id="429a6-194"> validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="429a6-195">Пример заголовка `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="429a6-195">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="429a6-196">Ошибки протокола WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="429a6-196">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="429a6-197">Ниже приведен список ограничений, относящихся к реализации ошибок протокола WS-ReliableMessaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-197">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="429a6-198">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="429a6-198">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="429a6-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создает `MessageNumberRollover` ошибок.</span><span class="sxs-lookup"><span data-stu-id="429a6-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="429a6-200">B1702: в SOAP 1.2, когда в конечной точке службы достигается максимальное число подключений и обработка новых подключений становится невозможной, среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает вложенный код ошибки `CreateSequenceRefused`, `netrm:ConnectionLimitReached`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="429a6-200">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="429a6-201">Ошибки WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="429a6-201">WS-Addressing Faults</span></span>  
 <span data-ttu-id="429a6-202">Поскольку протокол WS-ReliableMessaging использует протокол WS-Addressing, реализация WS-ReliableMessaging [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может создавать и передавать ошибки WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="429a6-202">Because WS-ReliableMessaging uses WS-Addressing, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="429a6-203">В этом разделе описаны ошибки WS-Addressing, которые среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]явным образом создает и передает на уровне WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="429a6-203">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="429a6-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает `Message Addressing Header Required` сбоя при выполнении одного из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="429a6-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="429a6-205">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `MessageId`;</span><span class="sxs-lookup"><span data-stu-id="429a6-205">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="429a6-206">в сообщении `CreateSequence`, `CloseSequence` или `TerminateSequence` отсутствует заголовок `ReplyTo`;</span><span class="sxs-lookup"><span data-stu-id="429a6-206">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="429a6-207">в сообщении `CreateSequenceResponse`, `CloseSequenceResponse` или `TerminateSequenceResponse` отсутствует заголовок `RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="429a6-207">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="429a6-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает `Endpoint Unavailable` ошибки для указания отсутствует конечная точка ожидает передачи данных, который может обрабатывать последовательности, основанной на изучение заголовки адресации в `CreateSequence` сообщения.</span><span class="sxs-lookup"><span data-stu-id="429a6-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="429a6-209">Сочетаемость протокола</span><span class="sxs-lookup"><span data-stu-id="429a6-209">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="429a6-210">Сочетаемость с WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="429a6-210">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-211"> поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации консорциума W3C по протоколу WS-Addressing версии 1.0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="429a6-211"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="429a6-212">Поскольку в спецификации протокола WS-ReliableMessaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="429a6-212">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="429a6-213">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-213">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="429a6-214">R2101: с протоколом WS-ReliableMessaging можно использовать как версию WS-Addressing 2004/08, так и версию WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="429a6-214">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="429a6-215">R2102: в рамках заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью механизма `Offer`, следует использовать только одну версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="429a6-215">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="429a6-216">Сочетаемость с SOAP</span><span class="sxs-lookup"><span data-stu-id="429a6-216">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-217"> поддерживает использование с протоколом WS-Reliable Messaging как версии SOAP 1.1, так и версии SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="429a6-217"> supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="429a6-218">Сочетаемость с WS-Security и WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="429a6-218">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-219"> обеспечивает защиту последовательностей WS-ReliableMessaging с помощью безопасного транспорта (HTTPS) и совместимости с протоколами WS-Security и WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="429a6-219"> provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="429a6-220">Протоколы WS-ReliableMessaging 1.1, WS-Security 1.1 и WS-Secure Conversation 1.3 необходимо использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="429a6-220">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="429a6-221">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-221">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="429a6-222">R2301: в дополнение к обеспечению целостности и конфиденциальности отдельных сообщений для защиты целостности последовательности WS-ReliableMessaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требуется использовать протокол WS-Secure.</span><span class="sxs-lookup"><span data-stu-id="429a6-222">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="429a6-223">R2302:AWS-Secure Conversation должен быть установлен до установки последовательностях WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="429a6-223">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="429a6-224">R2303: если время существования последовательности WS-ReliableMessaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="429a6-224">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="429a6-225">B2304:ws-последовательности ReliableMessaging или пары коррелированные встречные последовательности всегда привязан к одного сеанса WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="429a6-225">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="429a6-226">R2305: при использовании с протоколом WS-Secure Conversation респонденту [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] необходимо, чтобы сообщение `CreateSequence` содержало элемент `wsse:SecurityTokenReference` и заголовок `wsrm:UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="429a6-226">R2305: When composed with WS-Secure Conversation, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="429a6-227">Пример заголовка `UsesSequenceSTR`.</span><span class="sxs-lookup"><span data-stu-id="429a6-227">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="429a6-228">Сочетаемость с сеансами SSL/TLS</span><span class="sxs-lookup"><span data-stu-id="429a6-228">Composition with SSL/TLS sessions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-229"> не поддерживает совместное использование с сеансами SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="429a6-229"> does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="429a6-230">B2401: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются заголовки `wsrm:UsesSequenceSSL`.</span><span class="sxs-lookup"><span data-stu-id="429a6-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="429a6-231">R2402: инициатор системы надежного обмена сообщениями не должен отправлять сообщение `CreateSequence` с заголовком `wsrm:UsesSequenceSSL` респонденту [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-231">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="429a6-232">Сочетаемость с WS-Policy</span><span class="sxs-lookup"><span data-stu-id="429a6-232">Composition with WS-Policy</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-233"> поддерживает две версии протокола WS-Policy: WS-Policy 1.2 и WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="429a6-233"> supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="429a6-234">Утверждение WS-ReliableMessaging WS-Policy</span><span class="sxs-lookup"><span data-stu-id="429a6-234">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="429a6-235">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] утверждение WS-ReliableMessaging WS-Policy `wsrm:RMAssertion` используется для описания возможностей конечных точек.</span><span class="sxs-lookup"><span data-stu-id="429a6-235">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="429a6-236">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-236">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="429a6-237">B3001: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] к элементам `wsrmn:RMAssertion` прикрепляется проверочное утверждение WS-Policy `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="429a6-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-238"> поддерживает вложения в элементы `wsdl:binding` и `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="429a6-238"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="429a6-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] никогда не создает тег `wsp:Optional`.</span><span class="sxs-lookup"><span data-stu-id="429a6-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="429a6-240">B3003: при обращении к утверждению WS-Policy `wsrmp:RMAssertion` [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] игнорирует тег `wsp:Optional` и трактует политику WS-RM Policy как обязательную.</span><span class="sxs-lookup"><span data-stu-id="429a6-240">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="429a6-241">R3004: поскольку [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не может использоваться совместно с сеансами SSL/TLS, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не принимает политики, задающие `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="429a6-241">R3004: Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not compose with SSL/TLS sessions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="429a6-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создает элемент `wsrmp:DeliveryAssurance`.</span><span class="sxs-lookup"><span data-stu-id="429a6-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="429a6-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда задает гарантию доставки `wsrmp:ExactlyOnce`.</span><span class="sxs-lookup"><span data-stu-id="429a6-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="429a6-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к возникновению ошибки и считывает следующие свойства утверждения WS-ReliableMessaging и реализует контроль над ними на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="429a6-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="429a6-245">Пример `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="429a6-245">An example of a `RMAssertion`.</span></span>  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="429a6-246">Расширение WS-ReliableMessaging для управления потоком</span><span class="sxs-lookup"><span data-stu-id="429a6-246">Flow Control WS-ReliableMessaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-247"> использует расширяемость WS-ReliableMessaging, чтобы обеспечить более строгое управление над потоком последовательности сообщений.</span><span class="sxs-lookup"><span data-stu-id="429a6-247"> uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="429a6-248">Включить управление потоком, задав `ReliableSessionBindingElement` `FlowControlEnabled``boolean` свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="429a6-248">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="429a6-249">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="429a6-249">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="429a6-250">B4001: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `netrm:BufferRemaining`, используя возможности расширения элемента заголовка `SequenceAcknowledgement`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="429a6-250">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="429a6-251">B4002: даже если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требует наличия в заголовке `netrm:BufferRemaining` элемента `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="429a6-251">B4002: Even when Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="429a6-252">B4003: точка назначения системы надежного обмена сообщениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует элемент `netrm:BufferRemaining`, чтобы задать число новых сообщений, которые она может поместить в буфер.</span><span class="sxs-lookup"><span data-stu-id="429a6-252">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="429a6-253">Включен B4004:When надежного обмена сообщениями потока управления, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Источник надежного обмена сообщениями использует значение `netrm:BufferRemaining` регулирования передачу сообщений.</span><span class="sxs-lookup"><span data-stu-id="429a6-253">B4004:When Reliable Messaging Flow Control is enabled, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="429a6-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает целые значения элемента `netrm:BufferRemaining` в интервале от 0 до 4096 включительно и считывает целые значения в интервале от 0 до максимального значения типа `xs:int` (`maxInclusive`, 214748364) включительно.</span><span class="sxs-lookup"><span data-stu-id="429a6-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="429a6-255">Шаблоны обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="429a6-255">Message Exchange Patterns</span></span>  
 <span data-ttu-id="429a6-256">В этом разделе описана работа среды [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании протокола WS-ReliableMessaging для различных шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="429a6-256">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="429a6-257">Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:</span><span class="sxs-lookup"><span data-stu-id="429a6-257">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="429a6-258">неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;</span><span class="sxs-lookup"><span data-stu-id="429a6-258">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="429a6-259">адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.</span><span class="sxs-lookup"><span data-stu-id="429a6-259">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="429a6-260">Односторонний неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="429a6-260">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="429a6-261">Привязка</span><span class="sxs-lookup"><span data-stu-id="429a6-261">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-262"> поддерживает шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="429a6-262"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-263"> использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="429a6-263"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="429a6-264">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-264">CreateSequence Exchange</span></span>  
 <span data-ttu-id="429a6-265">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` без элемента `Offer` в HTTP-запросе и ожидает сообщения `CreateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-265">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="429a6-266">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-266">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="429a6-267">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="429a6-267">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="429a6-268">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает подтверждения при ответе на все сообщения, кроме сообщения `CreateSequence` и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="429a6-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="429a6-269">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда передает отдельное подтверждение в HTTP-ответе для всех сообщений последовательности и сообщений `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="429a6-269">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="429a6-270">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-270">CloseSequence Exchange</span></span>  
 <span data-ttu-id="429a6-271">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CloseSequence` в HTTP-запросе и ожидает сообщения `CreateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-271">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="429a6-272">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CloseSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-272">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="429a6-273">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-273">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="429a6-274">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequence` в HTTP-запросе и ожидает сообщения `TerminateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="429a6-275">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="429a6-276">Односторонний адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="429a6-276">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="429a6-277">Привязка</span><span class="sxs-lookup"><span data-stu-id="429a6-277">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-278"> поддерживает шаблон одностороннего обмена сообщениями с использованием одной последовательности через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="429a6-278"> provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-279"> использует для передачи всех сообщений HTTP-запросы.</span><span class="sxs-lookup"><span data-stu-id="429a6-279"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="429a6-280">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="429a6-280">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="429a6-281">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-281">CreateSequence Exchange</span></span>  
 <span data-ttu-id="429a6-282">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` без элемента `Offer` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="429a6-282">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="429a6-283">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает последовательность и передает сообщение `CreateSequenceResponse` без элемента `Accept` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="429a6-283">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="429a6-284">Дуплексный адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="429a6-284">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="429a6-285">Привязка</span><span class="sxs-lookup"><span data-stu-id="429a6-285">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-286"> поддерживает шаблон полностью асинхронного двустороннего обмена сообщениями с использованием двух последовательностей через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="429a6-286"> provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="429a6-287">Этот шаблон обмена сообщениями можно ограниченным образом объединить с инициатором шаблоном двустороннего обмена сообщениями `Request/Reply`, `Addressable`.</span><span class="sxs-lookup"><span data-stu-id="429a6-287">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-288"> использует для передачи всех сообщений HTTP-запросы.</span><span class="sxs-lookup"><span data-stu-id="429a6-288"> uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="429a6-289">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="429a6-289">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="429a6-290">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-290">CreateSequence Exchange</span></span>  
 <span data-ttu-id="429a6-291">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` с элементом `Offer` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="429a6-291">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="429a6-292">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что сообщение `CreateSequence` содержит элемент `Offer`, после чего создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept`.</span><span class="sxs-lookup"><span data-stu-id="429a6-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="429a6-293">Время существования последовательности</span><span class="sxs-lookup"><span data-stu-id="429a6-293">Sequence Lifetime</span></span>  
 <span data-ttu-id="429a6-294">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] две последовательности рассматриваются в качестве одного полностью двустороннего сеанса.</span><span class="sxs-lookup"><span data-stu-id="429a6-294">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="429a6-295">После разрыва одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает, что удаленная точка доступа вызовет разрыв в обеих последовательностях.</span><span class="sxs-lookup"><span data-stu-id="429a6-295">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="429a6-296">После чтения разрыва в одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вызывает разрывы в обеих последовательностях.</span><span class="sxs-lookup"><span data-stu-id="429a6-296">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-297"> может закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности.</span><span class="sxs-lookup"><span data-stu-id="429a6-297"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="429a6-298">И наоборот, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.</span><span class="sxs-lookup"><span data-stu-id="429a6-298">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="429a6-299">Односторонний обмен сообщениями запрос-ответ, неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="429a6-299">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="429a6-300">Привязка</span><span class="sxs-lookup"><span data-stu-id="429a6-300">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-301"> поддерживает шаблон одностороннего обмена сообщениями «запрос-ответ» с использованием двух последовательностей через один канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="429a6-301"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-302"> использует HTTP-запросы для передачи всех сообщений от инициатора респонденту и HTTP-ответы для передачи всех сообщений от респондента инициатору.</span><span class="sxs-lookup"><span data-stu-id="429a6-302"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="429a6-303">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-303">CreateSequence Exchange</span></span>  
 <span data-ttu-id="429a6-304">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` с элементом `Offer` в HTTP-запросе и ожидает сообщения `CreateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-304">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="429a6-305">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-305">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="429a6-306">Односторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="429a6-306">One-way Message</span></span>  
 <span data-ttu-id="429a6-307">Для одностороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает отдельное сообщение `SequenceAcknowledgement` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-307">To complete a one-way message exchange successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="429a6-308">Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="429a6-308">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="429a6-309">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="429a6-309">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="429a6-310">Двусторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="429a6-310">Two Way Messages</span></span>  
 <span data-ttu-id="429a6-311">Для реализации протокола двустороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает сообщение последовательности ответов в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-311">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="429a6-312">Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.</span><span class="sxs-lookup"><span data-stu-id="429a6-312">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="429a6-313">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="429a6-313">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="429a6-314">Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.</span><span class="sxs-lookup"><span data-stu-id="429a6-314">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="429a6-315">Повторные попытки ответов</span><span class="sxs-lookup"><span data-stu-id="429a6-315">Retrying Replies</span></span>  
 <span data-ttu-id="429a6-316">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для обеспечения корреляции между сообщениями протокола двустороннего обмена сообщениями используется корреляция между HTTP-запросами и ответами.</span><span class="sxs-lookup"><span data-stu-id="429a6-316">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="429a6-317">Поэтому инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не прекращает попытки отправки сообщения последовательности запросов в случае подтверждения этого сообщения, а дожидается HTTP-ответа, содержащего элемент `SequenceAcknowledgement`, ответ приложения или ошибку.</span><span class="sxs-lookup"><span data-stu-id="429a6-317">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="429a6-318">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] повторяет в HTTP-ответе ответы на запрос, с которым связан этот ответ.</span><span class="sxs-lookup"><span data-stu-id="429a6-318">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="429a6-319">Обмен сообщениями CloseSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-319">CloseSequence Exchange</span></span>  
 <span data-ttu-id="429a6-320">После получения всех сообщений последовательности ответов и подтверждений для всех сообщений односторонней последовательности запросов инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в HTTP-запросе передает сообщение `CloseSequence` для данной последовательности запросов и ожидает сообщения `CloseSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-320">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="429a6-321">Закрытие последовательности запросов неявным образом закрывает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="429a6-321">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="429a6-322">Это значит, что инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] включает последнее подтверждение `SequenceAcknowledgement` последовательности ответов в сообщение `CloseSequence`, а в последовательности ответов нет ответного сообщения `CloseSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-322">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="429a6-323">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет все ответы и подтверждения и в HTTP-ответе передает сообщение `CloseSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="429a6-323">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="429a6-324">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-324">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="429a6-325">После получения сообщения `CloseSequenceResponse` инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequence` для последовательности запросов в HTTP-запросе и ожидает сообщения `TerminateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-325">After receiving the `CloseSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="429a6-326">Как и в случае обмена сообщениями `CloseSequence` завершение последовательности запросов неявным образом завершает последовательность ответов.</span><span class="sxs-lookup"><span data-stu-id="429a6-326">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="429a6-327">Это значит, что инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] включает последнее подтверждение `SequenceAcknowledgement` последовательности ответов в сообщение `TerminateSequence`, и что в последовательности ответов нет ответного сообщения `TerminateSequence`.</span><span class="sxs-lookup"><span data-stu-id="429a6-327">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="429a6-328">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `TerminateSequenceResponse` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="429a6-328">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="429a6-329">Обмен сообщениями запрос-ответ, адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="429a6-329">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="429a6-330">Привязка</span><span class="sxs-lookup"><span data-stu-id="429a6-330">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-331"> поддерживает шаблон обмена сообщениями запрос-ответ с использованием двух последовательностей через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="429a6-331"> provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="429a6-332">Этот шаблон обмена сообщениями можно ограниченным образом объединить с шаблоном инициатора по двустороннему обмену сообщениями `Duplex, Addressable`.</span><span class="sxs-lookup"><span data-stu-id="429a6-332">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-333"> использует для передачи всех сообщений HTTP-запросы.</span><span class="sxs-lookup"><span data-stu-id="429a6-333"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="429a6-334">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="429a6-334">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="429a6-335">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="429a6-335">CreateSequence Exchange</span></span>  
 <span data-ttu-id="429a6-336">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequence` с элементом `Offer` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="429a6-336">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="429a6-337">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что сообщение `CreateSequence` содержит элемент `Offer`, после чего создает последовательность и передает сообщение `CreateSequenceResponse` с элементом `Accept`.</span><span class="sxs-lookup"><span data-stu-id="429a6-337">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="429a6-338">Корреляция запросов и ответов</span><span class="sxs-lookup"><span data-stu-id="429a6-338">Request/Reply Correlation</span></span>  
 <span data-ttu-id="429a6-339">Следующие действия относятся ко всем связанным запросам и ответам.</span><span class="sxs-lookup"><span data-stu-id="429a6-339">The following applies to all correlated requests and replies:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-340"> проверяет, что все сообщения с запросами приложения содержат ссылку на конечную точку `ReplyTo` и значение `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="429a6-340"> ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-341"> применяет ссылку на локальную конечную точку в качестве значения `ReplyTo` каждого сообщения с запросом приложения.</span><span class="sxs-lookup"><span data-stu-id="429a6-341"> applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="429a6-342">Ссылка на локальную конечную точку является значением `CreateSequence` сообщения `ReplyTo` для инициатора и значением `CreateSequence` сообщения `To` для респондента.</span><span class="sxs-lookup"><span data-stu-id="429a6-342">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-343"> проверяет, что все сообщения входящих запросов содержат значения `MessageId` и `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="429a6-343"> ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-344"> проверяет, что значения универсальных кодов ресурсов (URI) в ссылке на конечную точку `ReplyTo` всех сообщений запросов приложения совпадают с определенной выше ссылкой на локальную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="429a6-344"> ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="429a6-345"> проверяет, что все ответы содержат правильные заголовки `RelatesTo` и `To`, соответствующие правилам связывания запросов и ответов `wsa`.</span><span class="sxs-lookup"><span data-stu-id="429a6-345"> ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
