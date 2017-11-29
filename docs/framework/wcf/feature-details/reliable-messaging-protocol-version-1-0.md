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
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="0c1f0-102">Протокол надежного обмена сообщениями, версия 1.0</span><span class="sxs-lookup"><span data-stu-id="0c1f0-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="0c1f0-103">В этом разделе описаны особенности реализации в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] протокола обмена сообщениями WS-Reliable (версия 1.0 от февраля 2005 года), необходимого для взаимодействия с использованием транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="0c1f0-104">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] соблюдена спецификация обмена сообщениями WS-Reliable с определенными ограничениями и пояснениями, описанными далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="0c1f0-105">Обратите внимание, что протокол WS-ReliableMessaging версии 1.0 реализуется начиная с версии [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="0c1f0-106">Версия протокола WS-Reliable Messaging от февраля 2005 г. реализована в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью класса <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-106">The WS-Reliable Messaging February 2005 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="0c1f0-107">Для удобства объяснения в этом разделе используются следующие роли:</span><span class="sxs-lookup"><span data-stu-id="0c1f0-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="0c1f0-108">инициатор: клиент, инициирующий создание последовательности сообщений WS-Reliable;</span><span class="sxs-lookup"><span data-stu-id="0c1f0-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
-   <span data-ttu-id="0c1f0-109">респондент: служба, получающая запросы инициатора.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="0c1f0-110">В этом документе используются префиксы и пространства имен, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="0c1f0-111">Префикс</span><span class="sxs-lookup"><span data-stu-id="0c1f0-111">Prefix</span></span>|<span data-ttu-id="0c1f0-112">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0c1f0-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="0c1f0-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="0c1f0-113">wsrm</span></span>|<span data-ttu-id="0c1f0-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span><span class="sxs-lookup"><span data-stu-id="0c1f0-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span></span>|  
|<span data-ttu-id="0c1f0-115">netrm</span><span class="sxs-lookup"><span data-stu-id="0c1f0-115">netrm</span></span>|<span data-ttu-id="0c1f0-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="0c1f0-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="0c1f0-117">s</span><span class="sxs-lookup"><span data-stu-id="0c1f0-117">s</span></span>|<span data-ttu-id="0c1f0-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="0c1f0-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="0c1f0-119">wsa</span><span class="sxs-lookup"><span data-stu-id="0c1f0-119">wsa</span></span>|<span data-ttu-id="0c1f0-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="0c1f0-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="0c1f0-121">wsse</span><span class="sxs-lookup"><span data-stu-id="0c1f0-121">wsse</span></span>|<span data-ttu-id="0c1f0-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="0c1f0-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="0c1f0-123">Обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="0c1f0-123">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="0c1f0-124">Сообщения установления последовательности</span><span class="sxs-lookup"><span data-stu-id="0c1f0-124">Sequence Establishment Messages</span></span>  
 <span data-ttu-id="0c1f0-125">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализованы сообщения `CreateSequence` и `CreateSequenceResponse`, позволяющие установить последовательность надежных сообщений.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-125">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="0c1f0-126">Действуют следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-126">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="0c1f0-127">B1101: инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создает необязательный элемент "Expires" в сообщении `CreateSequence` или, если сообщение `CreateSequence` содержит элемент `Offer`, необязательный элемент `Expires` в элементе `Offer`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-127">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
-   <span data-ttu-id="0c1f0-128">B1102: при обращении к сообщению `CreateSequence` инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` отправляет и получает оба элемента `Expires`, если они существуют, но не использует их значения.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-128">B1102: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="0c1f0-129">Протокол WS-Reliable Messaging использует механизм `Offer` для формирования двух коррелированных встречных последовательностей, которые составляют сеанс.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-129">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="0c1f0-130">R1103: если сообщение `CreateSequence` содержит элемент `Offer`, респондент системы надежного обмена сообщениями должен либо принять последовательности и выдать ответ `CreateSequenceResponse`, который содержит элемент `wsrm:Accept`, образующий две коррелированных встречных последовательности, либо отклонить запрос `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-130">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
-   <span data-ttu-id="0c1f0-131">R1104: `SequenceAcknowledgement` и сообщения приложения, передаваемые во встречной последовательности, должны быть отправлены по адресу ссылки конечной последовательности `ReplyTo` в `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-131">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="0c1f0-132">R1105: адреса ссылок на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны совпадать на уровне октетов.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-132">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="0c1f0-133">Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, чтобы совпадал фрагмент ссылки на конечные точки `AcksTo` и `ReplyTo`, обозначающий универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="0c1f0-133">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="0c1f0-134">R1106: ссылки на конечные точки `AcksTo` и `ReplyTo` в сообщении `CreateSequence` должны иметь один и тот же набор параметров ссылок.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-134">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     <span data-ttu-id="0c1f0-135">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предполагается, что [параметры ссылок] `AcksTo` и `ReplyTo` в сообщении `CreateSequence` совпадают и используют [параметры ссылок] из ссылки на конечную точку `ReplyTo` в подтверждениях и сообщениях встречной последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-135">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="0c1f0-136">R1107: при установке двух встречных последовательностей с помощью механизма `Offer` сообщение `SequenceAcknowledgement` и сообщения приложения во встречных последовательностях должны отправляться по ссылке на конечную точку `ReplyTo` в сообщении `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-136">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="0c1f0-137">R1108: при установке двух встречных последовательностей с помощью механизма "Offer" свойство `[address]` дочернего элемента ссылки на конечную точку `wsrm:AcksTo` элемента `wsrm:Accept` в сообщении `CreateSequenceResponse` должно с точностью до байта совпадать с универсальным кодом ресурса (URI) назначения сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-137">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="0c1f0-138">R1109: при установке двух встречных последовательностей с помощью механизма `Offer` сообщения, отправленные инициатором, и подтверждения на сообщения респондента должны отправляться по одной и той же ссылке на конечную точку.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-138">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     <span data-ttu-id="0c1f0-139">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] протокол WS-Reliable Messaging используется для установки надежных сеансов между инициатором и респондентом.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-139">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="0c1f0-140">Реализация протокола WS-Reliable Messaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обеспечивает создание надежного сеанса для односторонней связи, обмена запросами и ответами и для полнодуплексного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-140">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="0c1f0-141">WS-Reliable Messaging `Offer` с помощью механизма `CreateSequence` / `CreateSequenceResponse` позволяет устанавливать две коррелированные встречные последовательности и обеспечивает протокол сеанса, которая подходит для всех конечных точках обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-141">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="0c1f0-142">Поскольку платформа [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] гарантирует безопасность таких сеансов, включая сквозную защиту для обеспечения целостности сеанса, она позволяет проверять, что сообщения, предназначенные одной и той же стороне, достигнут одной и той точки назначения.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-142">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="0c1f0-143">Кроме того, это делает возможным передачу подтверждений последовательностей в сообщениях приложений.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-143">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="0c1f0-144">Таким образом, ограничения R1104, R1105 и R1108 относятся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-144">Therefore, constraints R1104, R1105, and R1108 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="0c1f0-145">Пример сообщения `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-145">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="0c1f0-146">Пример сообщения `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-146">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="sequence"></a><span data-ttu-id="0c1f0-147">Sequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-147">Sequence</span></span>  
 <span data-ttu-id="0c1f0-148">Ниже приведен список ограничений, относящихся к последовательностям.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-148">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="0c1f0-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к возникновению ошибки и обращается к порядковые номера не выше, чем `xs:long`максимальное значение включительно, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
-   <span data-ttu-id="0c1f0-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создает пустой последним сообщением с URI действия http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates an empty-bodied last message with the action URI of http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
-   <span data-ttu-id="0c1f0-151">B1203: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сообщение получается и отправляется с заголовком последовательности, содержащим элемент `LastMessage`, при условии, что значение универсального кода ресурса (URI) действия не равно http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
 <span data-ttu-id="0c1f0-152">Пример заголовка последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-152">An example of a Sequence Header.</span></span>  
  
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
  
### <a name="ackrequested-header"></a><span data-ttu-id="0c1f0-153">Заголовок AckRequested</span><span class="sxs-lookup"><span data-stu-id="0c1f0-153">AckRequested Header</span></span>  
 <span data-ttu-id="0c1f0-154">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в качестве механизма поддержки активности используется заголовок `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-154">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="0c1f0-155">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создается необязательный элемент `MessageNumber`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-155">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="0c1f0-156">При получении сообщения с заголовком `AckRequested`, содержащим элемент `MessageNumber`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] игнорирует значение элемента `MessageNumber`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-156">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="0c1f0-157">Заголовок SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="0c1f0-157">SequenceAcknowledgement Header</span></span>  
 <span data-ttu-id="0c1f0-158">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для передачи подтверждений последовательностей протокола WS-Reliable Messaging используются сообщения приложений.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-158">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="0c1f0-159">R1401: при установке двух встречных последовательностей с помощью механизма `Offer` заголовок `SequenceAcknowledgement` может включаться в любое сообщение приложения, передаваемое определенному получателю.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-159">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
-   <span data-ttu-id="0c1f0-160">B1402: когда в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] необходимо создать подтверждение перед получением любых сообщений последовательности (например, чтобы соответствовать требованиям сообщения `AckRequested`), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает заголовок `SequenceAcknowledgement`, содержащий диапазон 0-0, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-160">B1402: When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="0c1f0-161">B1403: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются заголовки `SequenceAcknowledgement`, содержащие элемент `Nack`, но поддерживаются элементы `Nack`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="0c1f0-162">Ошибки протокола WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="0c1f0-162">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="0c1f0-163">Ниже приведен список ограничений, относящихся к реализации ошибок протокола WS-Reliable Messaging в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-163">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-Reliable Messaging faults:</span></span>  
  
-   <span data-ttu-id="0c1f0-164">B1501: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не создаются ошибки `MessageNumberRollover`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="0c1f0-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может создать конечную точку `CreateSequenceRefused` ошибок, как описано в спецификации.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
-   <span data-ttu-id="0c1f0-166">B1503:When конечной точки службы достигает этого значения подключения и не может обработать новые подключения, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к возникновению дополнительного `CreateSequenceRefused` код, ошибки `netrm:ConnectionLimitReached`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-166">B1503:When the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="0c1f0-167">Ошибки WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="0c1f0-167">WS-Addressing Faults</span></span>  
 <span data-ttu-id="0c1f0-168">Поскольку протокол WS-Reliable Messaging использует протокол WS-Addressing, реализация WS-Reliable Messaging [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может создавать и передавать ошибки WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-168">Because WS-Reliable Messaging uses WS-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="0c1f0-169">В этом разделе описаны ошибки WS-Addressing, которые среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]явным образом создает и передает на уровне WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-169">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
-   <span data-ttu-id="0c1f0-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] формирует ошибку, требуется адресация заголовок сообщения в том случае, если выполняется одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="0c1f0-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="0c1f0-171">в сообщении отсутствуют заголовки `Sequence` и `Action`;</span><span class="sxs-lookup"><span data-stu-id="0c1f0-171">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    -   <span data-ttu-id="0c1f0-172">в сообщении `CreateSequence` отсутствует заголовок `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-172">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="0c1f0-173">в сообщении `CreateSequence` отсутствует заголовок `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-173">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
-   <span data-ttu-id="0c1f0-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] формирует ошибку, действие не поддерживается в ответ на сообщение, которое отсутствует `Sequence` заголовок и имеет `Action` заголовок, который не распознается в спецификации WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
-   <span data-ttu-id="0c1f0-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] формирует ошибку, конечная точка недоступна для указания, что конечной точки не обрабатывает последовательность на основании проверки `CreateSequence` заголовков адресов в сообщении.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="0c1f0-176">Сочетаемость протокола</span><span class="sxs-lookup"><span data-stu-id="0c1f0-176">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="0c1f0-177">Сочетаемость с WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="0c1f0-177">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-178"> поддерживает две версии протокола WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] и рекомендации консорциума W3C по протоколу WS-Addressing версии 1.0 [WS-ADDR-CORE] и [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-178"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="0c1f0-179">Поскольку в спецификации протокола WS-Reliable Messaging указана только версия WS-Addressing 2004/08, он не накладывает ограничений на используемую версию WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-179">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="0c1f0-180">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-180">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="0c1f0-181">R2101: как можно использовать с WS-Reliable Messaging WS-Addressing 2004/08 и WS-Addressing 1.0.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-181">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="0c1f0-182">Необходимо использовать одну версию WS-Addressing R2102:A во всей заданной последовательности WS-ReliableMessaging или пары встречных последовательностей, связанных с помощью `wsrm:Offer` механизм.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-182">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="0c1f0-183">Сочетаемость с SOAP</span><span class="sxs-lookup"><span data-stu-id="0c1f0-183">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-184"> поддерживает использование с протоколом WS-Reliable Messaging как версии SOAP 1.1, так и версии SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-184"> supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="0c1f0-185">Сочетаемость с WS-Security и WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="0c1f0-185">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-186"> обеспечивает защиту последовательностей WS-Reliable Messaging с помощью безопасного транспорта (HTTPS) и совместимости с протоколами WS-Security и WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-186"> provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="0c1f0-187">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-187">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="0c1f0-188">R2301: для защиты целостности последовательности WS-Reliable Messaging в дополнение к целостности и конфиденциальности отдельных сообщений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует, что необходимо использовать WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-188">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="0c1f0-189">R2302:AWS-Secure Conversation должен быть установлен до установки последовательностях WS-Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-189">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
-   <span data-ttu-id="0c1f0-190">R2303: если время существования последовательности WS-Reliable Messaging превышает время существования сеанса WS-Secure Conversation, необходимо с помощью привязки обновления WS-Secure Conversation обновить маркер `SecurityContextToken`, созданный протоколом WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-190">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="0c1f0-191">B2304:ws-последовательности системы надежного обмена сообщениями или пару коррелированные встречные последовательности всегда привязан к одного сеанса WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-191">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="0c1f0-192">Источник в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `wsse:SecurityTokenReference`, используя раздел расширения элемента заголовка в сообщении `CreateSequence`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-192">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="0c1f0-193">Сочетание с WS-Secure Conversation R2305:When `CreateSequence` сообщение должно содержать `wsse:SecurityTokenReference` элемента.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-193">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="0c1f0-194">Утверждение WS-Reliable Messaging WS-Policy</span><span class="sxs-lookup"><span data-stu-id="0c1f0-194">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 <span data-ttu-id="0c1f0-195">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] утверждение WS-Reliable Messaging WS-Policy `wsrm:RMAssertion` используется для описания возможностей конечных точек.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-195">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="0c1f0-196">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-196">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="0c1f0-197">B3001: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] к элементам `wsrm:RMAssertion` прикрепляется проверочное утверждение WS-Policy `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-198"> поддерживает вложения в элементы `wsdl:binding` и `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-198"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="0c1f0-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает следующие дополнительные свойства утверждения WS-Reliable Messaging и реализует контроль над ними через элемент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="0c1f0-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:</span></span>  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="0c1f0-200">Пример.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-200">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="0c1f0-201">Расширение WS-Reliable Messaging для управления потоком</span><span class="sxs-lookup"><span data-stu-id="0c1f0-201">Flow Control WS-Reliable Messaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-202"> использует расширяемость WS-Reliable Messaging, чтобы обеспечить более строгий контроль над потоком сообщений последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-202"> uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="0c1f0-203">Включить управление потоком, задав `ReliableSessionBindingElement` `FlowControlEnabled``bool` свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-203">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``bool` property to `true`.</span></span> <span data-ttu-id="0c1f0-204">Ниже приведен список ограничений, относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c1f0-204">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="0c1f0-205">B4001: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает элемент `netrm:BufferRemaining`, используя возможности расширения элемента заголовка `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-205">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="0c1f0-206">B4002: если управление потоком системы надежного обмена сообщениями включено, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требует наличия элемента `netrm:BufferRemaining` в заголовке `SequenceAcknowledgement`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-206">B4002: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
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
  
-   <span data-ttu-id="0c1f0-207">B4003: в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется элемент `netrm:BufferRemaining`, чтобы задать количество новых сообщений, которые точка назначения системы надежного обмена сообщениями может поместить в буфер.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
-   <span data-ttu-id="0c1f0-208">B4004: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] надежного обмена сообщениями службы регулирует количество сообщений, передаваемых при приложения назначения надежного обмена сообщениями не может быстро получать сообщения.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-208">B4004:The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="0c1f0-209">Точка назначения системы надежного обмена сообщениями помещает сообщения в буфер, и значение элемента снижается до 0.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-209">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
-   <span data-ttu-id="0c1f0-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает целые значения элемента `netrm:BufferRemaining` в интервале от 0 до 4096 включительно и считывает целые значения в интервале от 0 до максимального значения типа `xs:int` (`maxInclusive`, 214748364) включительно.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="0c1f0-211">Шаблоны обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="0c1f0-211">Message Exchange Patterns</span></span>  
 <span data-ttu-id="0c1f0-212">В этом разделе описана работа среды [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании протокола WS-Reliable Messaging для различных шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-212">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="0c1f0-213">Для каждого шаблона обмена сообщениями рассматриваются два варианта развертывания:</span><span class="sxs-lookup"><span data-stu-id="0c1f0-213">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="0c1f0-214">неадресуемый инициатор - инициатор расположен за брандмауэром, респондент может отправлять инициатору сообщения только с HTTP-ответами;</span><span class="sxs-lookup"><span data-stu-id="0c1f0-214">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="0c1f0-215">адресуемый инициатор - как инициатор, так и респондент могут принимать HTTP-запросы, т. е. можно установить два встречных HTTP-подключения.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-215">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="0c1f0-216">Односторонний неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="0c1f0-216">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="0c1f0-217">Привязка</span><span class="sxs-lookup"><span data-stu-id="0c1f0-217">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-218"> поддерживает шаблон одностороннего обмена сообщениями с использованием одной последовательности через канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-218"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="0c1f0-219">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используются HTTP-запросы для передачи всех сообщений от диспетчеров ресурсов в RMD и HTTP-ответы для передачи всех сообщений от RMD к диспетчеру ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-219">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="0c1f0-220">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-220">CreateSequence Exchange</span></span>  
 <span data-ttu-id="0c1f0-221">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` без предложений.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-221">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="0c1f0-222">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` нет предложений перед созданием последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-222">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="0c1f0-223">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос `CreateSequence` сообщением `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-223">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="0c1f0-224">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="0c1f0-224">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="0c1f0-225">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает подтверждения при ответе на все сообщения, кроме сообщения `CreateSequence` и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-225">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="0c1f0-226">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] всегда создает отдельное подтверждение в HTTP-ответе для сообщений последовательности и сообщений `AckRequested`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-226">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="0c1f0-227">Сообщение TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-227">TerminateSequence message</span></span>  
 <span data-ttu-id="0c1f0-228">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сообщение `TerminateSequence` рассматривается как односторонняя операция, т.е. HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-228">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="0c1f0-229">Односторонний адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="0c1f0-229">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="0c1f0-230">Привязка</span><span class="sxs-lookup"><span data-stu-id="0c1f0-230">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-231"> поддерживает шаблон одностороннего обмена сообщениями через один входящий и один исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-231"> provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-232"> использует для передачи всех сообщений HTTP-запросы.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-232"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="0c1f0-233">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-233">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="0c1f0-234">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-234">CreateSequence Exchange</span></span>  
 <span data-ttu-id="0c1f0-235">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` без предложений.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-235">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="0c1f0-236">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` нет предложений перед созданием последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-236">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="0c1f0-237">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение `CreateSequenceResponse` в HTTP-запросе с помощью ссылки на конечную точку `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-237">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="0c1f0-238">Дуплексный адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="0c1f0-238">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="0c1f0-239">Привязка</span><span class="sxs-lookup"><span data-stu-id="0c1f0-239">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-240"> поддерживает шаблон полностью асинхронного двустороннего обмена сообщениями с использованием двух последовательностей через входящий и исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-240"> provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-241"> использует для передачи всех сообщений HTTP-запросы.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-241"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="0c1f0-242">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-242">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="0c1f0-243">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-243">CreateSequence Exchange</span></span>  
 <span data-ttu-id="0c1f0-244">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-244">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="0c1f0-245">Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-245">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-246"> отправляет сообщение `CreateSequenceResponse` в HTTP-запросе, направленном в конечную точку `CreateSequence` `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-246"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="0c1f0-247">Время существования последовательности</span><span class="sxs-lookup"><span data-stu-id="0c1f0-247">Sequence Lifetime</span></span>  
 <span data-ttu-id="0c1f0-248">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] две последовательности рассматриваются в качестве одного полнодуплексного сеанса.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-248">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="0c1f0-249">После разрыва одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ожидает, что удаленная точка доступа вызовет разрыв в обеих последовательностях.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-249">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="0c1f0-250">После чтения разрыва в одной последовательности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] вызывает разрывы в обеих последовательностях.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-250">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-251"> может закрыть исходящую последовательность и продолжать обработку сообщений во входящей последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-251"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="0c1f0-252">И наоборот, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может обработать закрытие входящей последовательности и продолжать отправку сообщений через исходящую последовательность.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-252">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="0c1f0-253">Обмен сообщениями запрос-ответ, неадресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="0c1f0-253">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="0c1f0-254">Привязка</span><span class="sxs-lookup"><span data-stu-id="0c1f0-254">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-255"> поддерживает шаблон одностороннего обмена сообщениями «запрос-ответ» с использованием двух последовательностей через один канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-255"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-256"> использует HTTP-запросы для передачи сообщений последовательности запросов и HTTP-ответы для передачи сообщений последовательности ответов.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-256"> uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="0c1f0-257">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="0c1f0-258">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="0c1f0-259">Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-259">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="0c1f0-260">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос `CreateSequence` сообщением `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-260">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="0c1f0-261">Односторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="0c1f0-261">One-way Message</span></span>  
 <span data-ttu-id="0c1f0-262">Для реализации протокола одностороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает отдельное сообщение `SequenceAcknowledgement` в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-262">To complete a one-way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="0c1f0-263">Сообщение `SequenceAcknowledgement` должно подтвердить передачу сообщения.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-263">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="0c1f0-264">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос подтверждением, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-264">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="0c1f0-265">Двусторонний обмен сообщениями</span><span class="sxs-lookup"><span data-stu-id="0c1f0-265">Two Way Messages</span></span>  
 <span data-ttu-id="0c1f0-266">Для реализации протокола двустороннего обмена сообщениями инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передает сообщение последовательности запросов в HTTP-запросе и получает сообщение последовательности ответов в HTTP-ответе.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-266">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="0c1f0-267">Ответ должен содержать подтверждение `SequenceAcknowledgement` того, что сообщение последовательности запросов было передано.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-267">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="0c1f0-268">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может ответить на запрос ответом приложения, ошибкой или ответом с пустым телом и кодом состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="0c1f0-269">Из-за наличия односторонних сообщений и временных параметров ответов приложения номера последовательности запросов и номера последовательности ответов не коррелируют между собой.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-269">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="0c1f0-270">Повторные попытки ответов</span><span class="sxs-lookup"><span data-stu-id="0c1f0-270">Retrying Replies</span></span>  
 <span data-ttu-id="0c1f0-271">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для обеспечения корреляции между сообщениями протокола двустороннего обмена сообщениями используется корреляция между HTTP-запросами и ответами.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-271">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="0c1f0-272">Поэтому инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не прекращает попытки отправки сообщения последовательности запросов в случае подтверждения этого сообщения, а дожидается HTTP-ответа, содержащего подтверждение, пользовательское сообщение или ошибку.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-272">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="0c1f0-273">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] повторяет в HTTP-запросе ответы на запрос, с которым коррелирует этот ответ.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-273">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="0c1f0-274">Обмен сообщениями LastMessage</span><span class="sxs-lookup"><span data-stu-id="0c1f0-274">LastMessage Exchange</span></span>  
 <span data-ttu-id="0c1f0-275">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает последнее сообщение с пустым телом в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-276"> ожидает ответ, но не учитывает само ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-276"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="0c1f0-277">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на запрос с последним пустым сообщением последовательности ответом с последним пустым сообщением последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-277">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="0c1f0-278">Если респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] получает последнее сообщение, в котором значение универсального кода ресурса (URI) действия отлично от http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает последним сообщением.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-278">If the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder receives a last message in which the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] replies with a last message.</span></span> <span data-ttu-id="0c1f0-279">В случае протокола двустороннего обмена сообщениями последнее сообщение содержит сообщение приложения, а в случае протокола одностороннего обмена сообщениями последнее сообщение будет пустым.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-279">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="0c1f0-280">Для респондента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не требуется подтверждение на ответ с последним пустым сообщением последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-280">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="0c1f0-281">Обмен сообщениями TerminateSequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-281">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="0c1f0-282">Когда на все запросы получен допустимый ответ, инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает и передает сообщение последовательности запросов `TerminateSequence` в HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-282">When all requests have received a valid reply, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-283"> ожидает ответ, но не учитывает само ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-283"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="0c1f0-284">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] отвечает на сообщение `TerminateSequence` последовательности запроса сообщением `TerminateSequence` последовательности запроса.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-284">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="0c1f0-285">В обычной последовательности отключения оба сообщения `TerminateSequence` содержат полный набор `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-285">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="0c1f0-286">Обмен сообщениями запрос-ответ, адресуемый инициатор</span><span class="sxs-lookup"><span data-stu-id="0c1f0-286">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="0c1f0-287">Привязка</span><span class="sxs-lookup"><span data-stu-id="0c1f0-287">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-288"> поддерживает шаблон обмена сообщениями «запрос-ответ» с использованием двух последовательностей через входящий и исходящий канал HTTP.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-288"> provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-289"> использует для передачи всех сообщений HTTP-запросы.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-289"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="0c1f0-290">Все HTTP-ответы имеют пустое тело и код состояния HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-290">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="0c1f0-291">Обмен сообщениями CreateSequence</span><span class="sxs-lookup"><span data-stu-id="0c1f0-291">CreateSequence Exchange</span></span>  
 <span data-ttu-id="0c1f0-292">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает сообщение `CreateSequence` с предложением.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="0c1f0-293">Перед созданием последовательности респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что в сообщении `CreateSequence` есть предложение.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-293">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="0c1f0-294"> отправляет сообщение `CreateSequenceResponse` в HTTP-запросе, направленном в конечную точку `CreateSequence` `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-294"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="0c1f0-295">Корреляция запросов и ответов</span><span class="sxs-lookup"><span data-stu-id="0c1f0-295">Request/Reply Correlation</span></span>  
 <span data-ttu-id="0c1f0-296">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что все сообщения с запросами приложения содержат значение `MessageId` и ссылку на конечную точку `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-296">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="0c1f0-297">Инициатор [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] применяет ссылку на конечную точку `CreateSequence` сообщения `ReplyTo` для каждого сообщения с запросом приложения.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="0c1f0-298">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует, чтобы все сообщения входящих запросов содержали значения `MessageId` и `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-298">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="0c1f0-299">Респондент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет, что значения универсальных кодов ресурсов (URI) для ссылки на конечную точку в сообщении `CreateSequence` и во всех сообщениях запросов приложения идентичны.</span><span class="sxs-lookup"><span data-stu-id="0c1f0-299">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
