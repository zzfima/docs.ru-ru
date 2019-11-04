---
title: Протоколы транзакций версии 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: 5ca0210c15afd6a3fc2e05bc3b9016a1fcd929b7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460274"
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="25223-102">Протоколы транзакций версии 1.0</span><span class="sxs-lookup"><span data-stu-id="25223-102">Transaction Protocols version 1.0</span></span>
<span data-ttu-id="25223-103">Windows Communication Foundation (WCF) версии 1 реализует протоколы WS-Atomic Transaction и WS-координации версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="25223-103">Windows Communication Foundation (WCF) version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> <span data-ttu-id="25223-104">Дополнительные сведения о версии 1,1 см. в разделе [Протоколы транзакций](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="25223-104">For more information about version 1.1, see [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="25223-105">Спецификация/документ</span><span class="sxs-lookup"><span data-stu-id="25223-105">Specification/Document</span></span>|<span data-ttu-id="25223-106">Ссылка</span><span class="sxs-lookup"><span data-stu-id="25223-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="25223-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="25223-107">WS-Coordination</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|<span data-ttu-id="25223-108">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="25223-108">WS-AtomicTransaction</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 <span data-ttu-id="25223-109">Согласно этим спецификациям протоколов, требуется взаимодействие на двух уровнях: между приложениями и между диспетчерами транзакций (см. следующий рисунок).</span><span class="sxs-lookup"><span data-stu-id="25223-109">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="25223-110">В спецификациях подробно описываются форматы сообщений и обмен сообщениями для обоих уровней взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="25223-110">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="25223-111">При обмене между приложениями применяются определенные средства обеспечения безопасности, надежности и методы кодирования, как и при обычном обмене в пределах сообщения.</span><span class="sxs-lookup"><span data-stu-id="25223-111">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="25223-112">Однако для успешного взаимодействия между диспетчерами транзакций требуется соглашение по конкретной привязке, поскольку она обычно не настраивается пользователем.</span><span class="sxs-lookup"><span data-stu-id="25223-112">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="25223-113">В этом разделе описываются состав спецификации протокола WS-Atomic Transaction (WS-AT) со средствами безопасности, а также безопасная привязка, используемая для обмена данными между диспетчерами транзакций.</span><span class="sxs-lookup"><span data-stu-id="25223-113">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="25223-114">Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination, включая IBM, IONA, Sun Microsystems и пр.</span><span class="sxs-lookup"><span data-stu-id="25223-114">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="25223-115">На следующем рисунке показано взаимодействие между двумя диспетчерами транзакций, диспетчером транзакций 1 и диспетчером транзакций 2, а также двумя приложениями, приложением 1 и приложением 2.</span><span class="sxs-lookup"><span data-stu-id="25223-115">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Снимок экрана, показывающий взаимодействие между диспетчерами транзакций.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="25223-117">Рассмотрим типовой сценарий WS-Coordination/WS-Atomic Transaction с одним инициатором (I) и одним участником (P).</span><span class="sxs-lookup"><span data-stu-id="25223-117">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="25223-118">И инициатор, и участник имеют диспетчеры транзакций (ITM и PTM, соответственно).</span><span class="sxs-lookup"><span data-stu-id="25223-118">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="25223-119">Двухфазная фиксация обозначается в этом разделе как 2PC.</span><span class="sxs-lookup"><span data-stu-id="25223-119">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25223-120">1. Креатекурдинатионконтекст</span><span class="sxs-lookup"><span data-stu-id="25223-120">1. CreateCoordinationContext</span></span>|<span data-ttu-id="25223-121">12. ответ на сообщение приложения</span><span class="sxs-lookup"><span data-stu-id="25223-121">12. Application Message Response</span></span>|  
|<span data-ttu-id="25223-122">2. Креатекурдинатионконтекстреспонсе</span><span class="sxs-lookup"><span data-stu-id="25223-122">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="25223-123">13. Фиксация (завершение)</span><span class="sxs-lookup"><span data-stu-id="25223-123">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="25223-124">3. Регистрация (завершение)</span><span class="sxs-lookup"><span data-stu-id="25223-124">3. Register (Completion)</span></span>|<span data-ttu-id="25223-125">14. подготовка (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-125">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="25223-126">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="25223-126">4. RegisterResponse</span></span>|<span data-ttu-id="25223-127">15. подготовка (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-127">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="25223-128">5. сообщение приложения</span><span class="sxs-lookup"><span data-stu-id="25223-128">5. Application Message</span></span>|<span data-ttu-id="25223-129">16. Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-129">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="25223-130">6. Креатекурдинатионконтекст с контекстом</span><span class="sxs-lookup"><span data-stu-id="25223-130">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="25223-131">17. подготовлено (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-131">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="25223-132">7. Регистрация (устойчивая)</span><span class="sxs-lookup"><span data-stu-id="25223-132">7. Register (Durable)</span></span>|<span data-ttu-id="25223-133">18. зафиксировано (завершение)</span><span class="sxs-lookup"><span data-stu-id="25223-133">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="25223-134">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="25223-134">8. RegisterResponse</span></span>|<span data-ttu-id="25223-135">19. Фиксация (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-135">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="25223-136">9. Креатекурдинатионконтекстреспонсе</span><span class="sxs-lookup"><span data-stu-id="25223-136">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="25223-137">20. Фиксация (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-137">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="25223-138">10. Регистрация (устойчивая)</span><span class="sxs-lookup"><span data-stu-id="25223-138">10. Register (Durable)</span></span>|<span data-ttu-id="25223-139">21. зафиксировано (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-139">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="25223-140">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="25223-140">11. RegisterResponse</span></span>|<span data-ttu-id="25223-141">22. зафиксировано (2PC)</span><span class="sxs-lookup"><span data-stu-id="25223-141">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="25223-142">В этом документе описываются состав спецификации протокола WS-AtomicTransaction со средствами безопасности, а также безопасная привязка, используемая для взаимодействия между диспетчерами транзакций.</span><span class="sxs-lookup"><span data-stu-id="25223-142">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="25223-143">Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="25223-143">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="25223-144">На рисунке и в таблице представлены четыре класса сообщений с точки зрения безопасности:</span><span class="sxs-lookup"><span data-stu-id="25223-144">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="25223-145">сообщения активации (CreateCoordinationContext и CreateCoordinationContextResponse);</span><span class="sxs-lookup"><span data-stu-id="25223-145">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="25223-146">сообщения регистрации (Register и RegisterResponse);</span><span class="sxs-lookup"><span data-stu-id="25223-146">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="25223-147">протокольные сообщения (Prepare, Rollback, Commit, Aborted и т. д.);</span><span class="sxs-lookup"><span data-stu-id="25223-147">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="25223-148">сообщения приложений.</span><span class="sxs-lookup"><span data-stu-id="25223-148">Application messages.</span></span>  
  
 <span data-ttu-id="25223-149">Первые три класса сообщений считаются сообщениями диспетчера транзакций и их конфигурация привязки описывается в разделе "Обмен сообщениями приложений" ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="25223-149">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="25223-150">Четвертый класс сообщений - это сообщения, передаваемые между приложениями, которые описываются в разделе "Примеры сообщений" ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="25223-150">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="25223-151">В этом разделе описываются привязки протоколов, используемые для каждого из этих классов в WCF.</span><span class="sxs-lookup"><span data-stu-id="25223-151">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="25223-152">Во всем данном документе используются следующие пространства имен XML и связанные с ними префиксы.</span><span class="sxs-lookup"><span data-stu-id="25223-152">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="25223-153">Префикс</span><span class="sxs-lookup"><span data-stu-id="25223-153">Prefix</span></span>|<span data-ttu-id="25223-154">Универсальный код ресурса (URI) пространства имен</span><span class="sxs-lookup"><span data-stu-id="25223-154">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="25223-155">s11</span><span class="sxs-lookup"><span data-stu-id="25223-155">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="25223-156">wsa</span><span class="sxs-lookup"><span data-stu-id="25223-156">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="25223-157">wscoor</span><span class="sxs-lookup"><span data-stu-id="25223-157">wscoor</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wscoor|  
|<span data-ttu-id="25223-158">wsat</span><span class="sxs-lookup"><span data-stu-id="25223-158">wsat</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wsat|  
|<span data-ttu-id="25223-159">т</span><span class="sxs-lookup"><span data-stu-id="25223-159">t</span></span>|http://schemas.xmlsoap.org/ws/2005/02/trust|  
|<span data-ttu-id="25223-160">o</span><span class="sxs-lookup"><span data-stu-id="25223-160">o</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="25223-161">xsd</span><span class="sxs-lookup"><span data-stu-id="25223-161">xsd</span></span>|http://www.w3.org/2001/XMLSchema|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="25223-162">Привязки диспетчеров транзакций</span><span class="sxs-lookup"><span data-stu-id="25223-162">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="25223-163">R1001: для обмена сообщениями протоколов WS-Atomic Transaction и WS-Coordination диспетчеры транзакций должны использовать SOAP 1.1 и WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="25223-163">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="25223-164">Сообщения приложений не ограничиваются этими привязками и описываются ниже.</span><span class="sxs-lookup"><span data-stu-id="25223-164">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="25223-165">Привязка HTTPS диспетчера транзакций</span><span class="sxs-lookup"><span data-stu-id="25223-165">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="25223-166">Для обеспечения безопасности и установления доверия между каждой парой "отправитель-получатель" в дереве транзакций привязка HTTPS диспетчера транзакций полагается только на механизм безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="25223-166">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="25223-167">Конфигурация транспорта HTTPS</span><span class="sxs-lookup"><span data-stu-id="25223-167">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="25223-168">Сертификаты X. 509 используются для установления удостоверения диспетчера транзакций.</span><span class="sxs-lookup"><span data-stu-id="25223-168">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="25223-169">Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации:</span><span class="sxs-lookup"><span data-stu-id="25223-169">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="25223-170">R1111: сертификаты X.509, представляемые по линии связи, должны иметь имя субъекта, соответствующее полному доменному имени исходного компьютера;</span><span class="sxs-lookup"><span data-stu-id="25223-170">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="25223-171">B1112: для успешного выполнения проверок имени субъекта X.509 между каждой парой "отправитель-получатель" в системе должна работать служба DNS.</span><span class="sxs-lookup"><span data-stu-id="25223-171">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="25223-172">Конфигурация привязки активации и регистрации</span><span class="sxs-lookup"><span data-stu-id="25223-172">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="25223-173">Для WCF требуется дуплексная привязка запроса/ответа с корреляцией по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="25223-173">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="25223-174">(Дополнительные сведения о корреляции и описание шаблонов обмена сообщениями "запрос-ответ" см. в разделе 8 спецификации WS-Atomic Transaction.)</span><span class="sxs-lookup"><span data-stu-id="25223-174">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="25223-175">Конфигурация привязки протокола 2PC</span><span class="sxs-lookup"><span data-stu-id="25223-175">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="25223-176">WCF поддерживает односторонние (датаграммы) сообщения по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="25223-176">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="25223-177">Корреляция между сообщениями зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="25223-177">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="25223-178">B2131: реализации должны поддерживать `wsa:ReferenceParameters`, как описано в разделе WS-Addressing для достижения корреляции сообщений 2PC WCF.</span><span class="sxs-lookup"><span data-stu-id="25223-178">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="25223-179">Привязка безопасности диспетчера транзакций смешанного режима</span><span class="sxs-lookup"><span data-stu-id="25223-179">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="25223-180">Это альтернативная привязка (смешанный режим), которая использует безопасность транспорта совместно с моделью выданного маркера WS-координации для целей идентификации.</span><span class="sxs-lookup"><span data-stu-id="25223-180">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="25223-181">В двух привязках отличаются только элементы "Активация" и "Регистрация".</span><span class="sxs-lookup"><span data-stu-id="25223-181">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="25223-182">Конфигурация транспорта HTTPS</span><span class="sxs-lookup"><span data-stu-id="25223-182">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="25223-183">Сертификаты X. 509 используются для установления удостоверения диспетчера транзакций.</span><span class="sxs-lookup"><span data-stu-id="25223-183">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="25223-184">Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="25223-184">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="25223-185">Конфигурация привязки сообщений активации</span><span class="sxs-lookup"><span data-stu-id="25223-185">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="25223-186">Сообщения активации обычно не участвуют во взаимодействии, поскольку они, как правило, передаются между приложением и его локальным диспетчером транзакций.</span><span class="sxs-lookup"><span data-stu-id="25223-186">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="25223-187">B1221: в WCF используется дуплексная HTTPS-привязка (описанная в разделе [протоколы обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) для сообщений активации.</span><span class="sxs-lookup"><span data-stu-id="25223-187">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="25223-188">Сообщения запроса и ответа коррелируются с помощью WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="25223-188">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="25223-189">В разделе 8 спецификации WS-Atomic Transaction приводятся дополнительные сведения о корреляции и шаблонах обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="25223-189">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="25223-190">R1222: при получении сообщения `CreateCoordinationContext` координатор должен выдать маркер `SecurityContextToken` со связанным с ним паролем `STx`.</span><span class="sxs-lookup"><span data-stu-id="25223-190">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="25223-191">Этот маркер возвращается в заголовке `t:IssuedTokens` согласно спецификации WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="25223-191">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="25223-192">R1223: если активация происходит в пределах существующего контекста координации, в сообщении `t:IssuedTokens` должен передаваться заголовок `SecurityContextToken` с маркером `CreateCoordinationContext`, связанным с существующим контекстом.</span><span class="sxs-lookup"><span data-stu-id="25223-192">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="25223-193">Для присоединения к исходящему сообщению `wscoor:CreateCoordinationContextResponse` необходимо создать заголовок `t:IssuedTokens`.</span><span class="sxs-lookup"><span data-stu-id="25223-193">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="25223-194">Конфигурация привязки сообщений регистрации</span><span class="sxs-lookup"><span data-stu-id="25223-194">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="25223-195">B1231: в WCF используется дуплексная привязка HTTPS (описывается в разделе [протоколы обмена сообщениями](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="25223-195">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="25223-196">Сообщения запроса и ответа коррелируются с помощью WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="25223-196">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="25223-197">В разделе 8 спецификации WS-AtomicTransaction приводятся дополнительные сведения о корреляции и описание шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="25223-197">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="25223-198">R1232: исходящие сообщения `wscoor:Register` должны использовать режим проверки подлинности `IssuedTokenOverTransport`, описанный в разделе [протоколы безопасности](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="25223-198">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="25223-199">Элемент `wsse:Timestamp` должен быть подписан с помощью выданного `SecurityContextToken STx`.</span><span class="sxs-lookup"><span data-stu-id="25223-199">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="25223-200">Эта подпись является доказательством владения маркером, связанным с конкретной транзакцией, и используется для проверки подлинности зачисления участника в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="25223-200">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="25223-201">Сообщение RegistrationResponse отправляется обратно по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="25223-201">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="25223-202">Конфигурация привязки протокола 2PC</span><span class="sxs-lookup"><span data-stu-id="25223-202">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="25223-203">WCF поддерживает односторонние (датаграммы) сообщения по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="25223-203">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="25223-204">Корреляция между сообщениями зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="25223-204">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="25223-205">B2131: реализации должны поддерживать `wsa:ReferenceParameters`, как описано в разделе WS-Addressing для достижения корреляции сообщений 2PC WCF.</span><span class="sxs-lookup"><span data-stu-id="25223-205">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="25223-206">Обмен сообщениями приложений</span><span class="sxs-lookup"><span data-stu-id="25223-206">Application Message Exchange</span></span>  
 <span data-ttu-id="25223-207">Для сообщений, передаваемых между приложениями, приложения могут использовать любую привязку, если она удовлетворяет следующим требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="25223-207">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="25223-208">R2001: заголовок сообщений, передаваемых между приложениями, должен содержать заголовок `t:IssuedTokens` наряду с `CoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="25223-208">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="25223-209">R2002: необходимо обеспечение целостности и конфиденциальности `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="25223-209">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="25223-210">Заголовок `CoordinationContext` содержит `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="25223-210">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="25223-211">Хотя определение `xsd:AnyURI` позволяет использовать как абсолютные, так и относительные URI, WCF поддерживает только `wscoor:Identifiers`, являющиеся абсолютными URI.</span><span class="sxs-lookup"><span data-stu-id="25223-211">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="25223-212">Если `wscoor:Identifier` `wscoor:CoordinationContext` является относительным URI, то ошибки будут возвращены из транзакционных служб WCF.</span><span class="sxs-lookup"><span data-stu-id="25223-212">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="25223-213">Примеры сообщений</span><span class="sxs-lookup"><span data-stu-id="25223-213">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="25223-214">Сообщения запроса и ответа CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="25223-214">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="25223-215">Следующие сообщения соответствуют шаблону "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="25223-215">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="25223-216">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="25223-216">CreateCoordinationContext</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="25223-217">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="25223-217">CreateCoordinationContextResponse</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="25223-218">Сообщения регистрации</span><span class="sxs-lookup"><span data-stu-id="25223-218">Registration Messages</span></span>  
 <span data-ttu-id="25223-219">Следующие сообщения являются сообщениями регистрации.</span><span class="sxs-lookup"><span data-stu-id="25223-219">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="25223-220">Регистровое</span><span class="sxs-lookup"><span data-stu-id="25223-220">Register</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a><span data-ttu-id="25223-221">Register Response</span><span class="sxs-lookup"><span data-stu-id="25223-221">Register Response</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="25223-222">Сообщения протокола двухфазной фиксации</span><span class="sxs-lookup"><span data-stu-id="25223-222">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="25223-223">Следующее сообщение относится к протоколу двухфазной фиксации (2PC).</span><span class="sxs-lookup"><span data-stu-id="25223-223">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="25223-224">Фиксация</span><span class="sxs-lookup"><span data-stu-id="25223-224">Commit</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="25223-225">Сообщения приложений</span><span class="sxs-lookup"><span data-stu-id="25223-225">Application Messages</span></span>  
 <span data-ttu-id="25223-226">Следующие сообщения являются сообщениями приложений.</span><span class="sxs-lookup"><span data-stu-id="25223-226">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="25223-227">Сообщение приложения - запрос</span><span class="sxs-lookup"><span data-stu-id="25223-227">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
