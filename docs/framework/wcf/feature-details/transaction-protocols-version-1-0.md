---
title: Протоколы транзакций версии 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: a19329b56bb569a04195b38877a42d635996ff1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184377"
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="71e26-102">Протоколы транзакций версии 1.0</span><span class="sxs-lookup"><span data-stu-id="71e26-102">Transaction Protocols version 1.0</span></span>
<span data-ttu-id="71e26-103">Windows Communication Foundation (WCF) версия 1 реализует версию 1.0 протоколов WS-Atomic Transaction и WS-Координация.</span><span class="sxs-lookup"><span data-stu-id="71e26-103">Windows Communication Foundation (WCF) version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> <span data-ttu-id="71e26-104">Для получения дополнительной информации о [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)версии 1.1 см.</span><span class="sxs-lookup"><span data-stu-id="71e26-104">For more information about version 1.1, see [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="71e26-105">Спецификация/документ</span><span class="sxs-lookup"><span data-stu-id="71e26-105">Specification/Document</span></span>|<span data-ttu-id="71e26-106">Ссылка</span><span class="sxs-lookup"><span data-stu-id="71e26-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="71e26-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="71e26-107">WS-Coordination</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|<span data-ttu-id="71e26-108">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="71e26-108">WS-AtomicTransaction</span></span>|<https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 <span data-ttu-id="71e26-109">Согласно этим спецификациям протоколов, требуется взаимодействие на двух уровнях: между приложениями и между диспетчерами транзакций (см. следующий рисунок).</span><span class="sxs-lookup"><span data-stu-id="71e26-109">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="71e26-110">В спецификациях подробно описываются форматы сообщений и обмен сообщениями для обоих уровней взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="71e26-110">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="71e26-111">При обмене между приложениями применяются определенные средства обеспечения безопасности, надежности и методы кодирования, как и при обычном обмене в пределах сообщения.</span><span class="sxs-lookup"><span data-stu-id="71e26-111">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="71e26-112">Однако для успешного взаимодействия между диспетчерами транзакций требуется соглашение по конкретной привязке, поскольку она обычно не настраивается пользователем.</span><span class="sxs-lookup"><span data-stu-id="71e26-112">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="71e26-113">В этом разделе описываются состав спецификации протокола WS-Atomic Transaction (WS-AT) со средствами безопасности, а также безопасная привязка, используемая для обмена данными между диспетчерами транзакций.</span><span class="sxs-lookup"><span data-stu-id="71e26-113">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="71e26-114">Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination, включая IBM, IONA, Sun Microsystems и пр.</span><span class="sxs-lookup"><span data-stu-id="71e26-114">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="71e26-115">Следующая цифра изображает совместимость между двумя менеджерами транзакций, менеджером транзакций 1 и менеджером транзакций 2, и двумя приложениями, Приложение 1 и Приложение 2:</span><span class="sxs-lookup"><span data-stu-id="71e26-115">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Скриншот, отображающие взаимодействие между менеджерами транзакций.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="71e26-117">Рассмотрим типовой сценарий WS-Coordination/WS-Atomic Transaction с одним инициатором (I) и одним участником (P).</span><span class="sxs-lookup"><span data-stu-id="71e26-117">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="71e26-118">И инициатор, и участник имеют диспетчеры транзакций (ITM и PTM, соответственно).</span><span class="sxs-lookup"><span data-stu-id="71e26-118">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="71e26-119">Двухфазная фиксация обозначается в этом разделе как 2PC.</span><span class="sxs-lookup"><span data-stu-id="71e26-119">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="71e26-120">1. СозданиеКоординацияКонтекст</span><span class="sxs-lookup"><span data-stu-id="71e26-120">1. CreateCoordinationContext</span></span>|<span data-ttu-id="71e26-121">12. Ответ на сообщение приложения</span><span class="sxs-lookup"><span data-stu-id="71e26-121">12. Application Message Response</span></span>|  
|<span data-ttu-id="71e26-122">2. СозданиеКоординационнаяКонтекстОтвет</span><span class="sxs-lookup"><span data-stu-id="71e26-122">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="71e26-123">13. Обязательство (Завершение)</span><span class="sxs-lookup"><span data-stu-id="71e26-123">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="71e26-124">3. Регистрация (Завершение)</span><span class="sxs-lookup"><span data-stu-id="71e26-124">3. Register (Completion)</span></span>|<span data-ttu-id="71e26-125">14. Подготовка (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-125">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="71e26-126">4. РегистрацияОтвет</span><span class="sxs-lookup"><span data-stu-id="71e26-126">4. RegisterResponse</span></span>|<span data-ttu-id="71e26-127">15. Подготовка (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-127">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="71e26-128">5. Сообщение приложения</span><span class="sxs-lookup"><span data-stu-id="71e26-128">5. Application Message</span></span>|<span data-ttu-id="71e26-129">16. Подготовлено (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-129">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="71e26-130">6. СозданиеКоординацияКонтекст с контекстом</span><span class="sxs-lookup"><span data-stu-id="71e26-130">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="71e26-131">17. Подготовлено (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-131">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="71e26-132">7. Регистрация (Долговечная)</span><span class="sxs-lookup"><span data-stu-id="71e26-132">7. Register (Durable)</span></span>|<span data-ttu-id="71e26-133">18. Совершенные (Завершение)</span><span class="sxs-lookup"><span data-stu-id="71e26-133">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="71e26-134">8. РегистрацияОтвет</span><span class="sxs-lookup"><span data-stu-id="71e26-134">8. RegisterResponse</span></span>|<span data-ttu-id="71e26-135">19. Обязательство (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-135">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="71e26-136">9. СозданиеКоординационнаяКонтекстОтвет</span><span class="sxs-lookup"><span data-stu-id="71e26-136">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="71e26-137">20. Обязательство (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-137">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="71e26-138">10. Регистрация (Долговечная)</span><span class="sxs-lookup"><span data-stu-id="71e26-138">10. Register (Durable)</span></span>|<span data-ttu-id="71e26-139">21. Совершенные (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-139">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="71e26-140">11. РегистрацияОтвет</span><span class="sxs-lookup"><span data-stu-id="71e26-140">11. RegisterResponse</span></span>|<span data-ttu-id="71e26-141">22. Совершенные (2PC)</span><span class="sxs-lookup"><span data-stu-id="71e26-141">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="71e26-142">В этом документе описываются состав спецификации протокола WS-AtomicTransaction со средствами безопасности, а также безопасная привязка, используемая для взаимодействия между диспетчерами транзакций.</span><span class="sxs-lookup"><span data-stu-id="71e26-142">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="71e26-143">Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="71e26-143">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="71e26-144">На рисунке и в таблице представлены четыре класса сообщений с точки зрения безопасности:</span><span class="sxs-lookup"><span data-stu-id="71e26-144">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="71e26-145">сообщения активации (CreateCoordinationContext и CreateCoordinationContextResponse);</span><span class="sxs-lookup"><span data-stu-id="71e26-145">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="71e26-146">сообщения регистрации (Register и RegisterResponse);</span><span class="sxs-lookup"><span data-stu-id="71e26-146">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="71e26-147">протокольные сообщения (Prepare, Rollback, Commit, Aborted и т. д.);</span><span class="sxs-lookup"><span data-stu-id="71e26-147">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="71e26-148">сообщения приложений.</span><span class="sxs-lookup"><span data-stu-id="71e26-148">Application messages.</span></span>  
  
 <span data-ttu-id="71e26-149">Первые три класса сообщений считаются сообщениями диспетчера транзакций и их конфигурация привязки описывается в разделе "Обмен сообщениями приложений" ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="71e26-149">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="71e26-150">Четвертый класс сообщений - это сообщения, передаваемые между приложениями, которые описываются в разделе "Примеры сообщений" ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="71e26-150">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="71e26-151">В этом разделе описаны протокольные привязки, используемые для каждого из этих классов WCF.</span><span class="sxs-lookup"><span data-stu-id="71e26-151">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="71e26-152">Во всем данном документе используются следующие пространства имен XML и связанные с ними префиксы.</span><span class="sxs-lookup"><span data-stu-id="71e26-152">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="71e26-153">Prefix</span><span class="sxs-lookup"><span data-stu-id="71e26-153">Prefix</span></span>|<span data-ttu-id="71e26-154">Универсальный код ресурса (URI) пространства имен</span><span class="sxs-lookup"><span data-stu-id="71e26-154">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="71e26-155">s11</span><span class="sxs-lookup"><span data-stu-id="71e26-155">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="71e26-156">wsa</span><span class="sxs-lookup"><span data-stu-id="71e26-156">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="71e26-157">wscoor</span><span class="sxs-lookup"><span data-stu-id="71e26-157">wscoor</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wscoor|  
|<span data-ttu-id="71e26-158">wsat</span><span class="sxs-lookup"><span data-stu-id="71e26-158">wsat</span></span>|http://schemas.xmlsoap.org/ws/2004/10/wsat|  
|<span data-ttu-id="71e26-159">t</span><span class="sxs-lookup"><span data-stu-id="71e26-159">t</span></span>|http://schemas.xmlsoap.org/ws/2005/02/trust|  
|<span data-ttu-id="71e26-160">o</span><span class="sxs-lookup"><span data-stu-id="71e26-160">o</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd|  
|<span data-ttu-id="71e26-161">xsd</span><span class="sxs-lookup"><span data-stu-id="71e26-161">xsd</span></span>|http://www.w3.org/2001/XMLSchema|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="71e26-162">Привязки диспетчеров транзакций</span><span class="sxs-lookup"><span data-stu-id="71e26-162">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="71e26-163">R1001: для обмена сообщениями протоколов WS-Atomic Transaction и WS-Coordination диспетчеры транзакций должны использовать SOAP 1.1 и WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="71e26-163">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="71e26-164">Сообщения приложений не ограничиваются этими привязками и описываются ниже.</span><span class="sxs-lookup"><span data-stu-id="71e26-164">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="71e26-165">Привязка HTTPS диспетчера транзакций</span><span class="sxs-lookup"><span data-stu-id="71e26-165">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="71e26-166">Для обеспечения безопасности и установления доверия между каждой парой "отправитель-получатель" в дереве транзакций привязка HTTPS диспетчера транзакций полагается только на механизм безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="71e26-166">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="71e26-167">Конфигурация транспорта HTTPS</span><span class="sxs-lookup"><span data-stu-id="71e26-167">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="71e26-168">Сертификаты X.509 используются для установления идентификации диспетчера транзакций.</span><span class="sxs-lookup"><span data-stu-id="71e26-168">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="71e26-169">Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации:</span><span class="sxs-lookup"><span data-stu-id="71e26-169">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="71e26-170">R1111: сертификаты X.509, представляемые по линии связи, должны иметь имя субъекта, соответствующее полному доменному имени исходного компьютера;</span><span class="sxs-lookup"><span data-stu-id="71e26-170">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="71e26-171">B1112: для успешного выполнения проверок имени субъекта X.509 между каждой парой "отправитель-получатель" в системе должна работать служба DNS.</span><span class="sxs-lookup"><span data-stu-id="71e26-171">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="71e26-172">Конфигурация привязки активации и регистрации</span><span class="sxs-lookup"><span data-stu-id="71e26-172">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="71e26-173">WCF требует привязки дуплекса запроса/ответа с корреляцией по HTTPS.</span><span class="sxs-lookup"><span data-stu-id="71e26-173">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="71e26-174">(Дополнительные сведения о корреляции и описание шаблонов обмена сообщениями "запрос-ответ" см. в разделе 8 спецификации WS-Atomic Transaction.)</span><span class="sxs-lookup"><span data-stu-id="71e26-174">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="71e26-175">Конфигурация привязки протокола 2PC</span><span class="sxs-lookup"><span data-stu-id="71e26-175">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="71e26-176">WCF поддерживает односторонние (данные) сообщения через HTTPS.</span><span class="sxs-lookup"><span data-stu-id="71e26-176">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="71e26-177">Корреляция между сообщениями зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="71e26-177">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="71e26-178">B2131: Реализация должна `wsa:ReferenceParameters` поддерживаться, как описано в WS-Addressing для достижения корреляции 2PC сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="71e26-178">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="71e26-179">Привязка безопасности диспетчера транзакций смешанного режима</span><span class="sxs-lookup"><span data-stu-id="71e26-179">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="71e26-180">Это альтернативный (смешанный режим) привязка, который использует транспортную безопасность в сочетании с моделью WS-Координация выпущенных токенов для целей создания идентификационных данных.</span><span class="sxs-lookup"><span data-stu-id="71e26-180">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="71e26-181">В двух привязках отличаются только элементы "Активация" и "Регистрация".</span><span class="sxs-lookup"><span data-stu-id="71e26-181">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="71e26-182">Конфигурация транспорта HTTPS</span><span class="sxs-lookup"><span data-stu-id="71e26-182">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="71e26-183">Сертификаты X.509 используются для установления идентификации диспетчера транзакций.</span><span class="sxs-lookup"><span data-stu-id="71e26-183">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="71e26-184">Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="71e26-184">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="71e26-185">Конфигурация привязки сообщений активации</span><span class="sxs-lookup"><span data-stu-id="71e26-185">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="71e26-186">Сообщения активации обычно не участвуют во взаимодействии, поскольку они, как правило, передаются между приложением и его локальным диспетчером транзакций.</span><span class="sxs-lookup"><span data-stu-id="71e26-186">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="71e26-187">B1221: WCF использует дуплексную привязку HTTPS (описанную в [протоколах обмена сообщениями)](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)для сообщений активации.</span><span class="sxs-lookup"><span data-stu-id="71e26-187">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="71e26-188">Сообщения запроса и ответа коррелируются с помощью WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="71e26-188">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="71e26-189">В разделе 8 спецификации WS-Atomic Transaction приводятся дополнительные сведения о корреляции и шаблонах обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="71e26-189">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="71e26-190">R1222: при получении сообщения `CreateCoordinationContext` координатор должен выдать маркер `SecurityContextToken` со связанным с ним паролем `STx`.</span><span class="sxs-lookup"><span data-stu-id="71e26-190">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="71e26-191">Этот маркер возвращается в заголовке `t:IssuedTokens` согласно спецификации WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="71e26-191">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="71e26-192">R1223: если активация происходит в пределах существующего контекста координации, в сообщении `t:IssuedTokens` должен передаваться заголовок `SecurityContextToken` с маркером `CreateCoordinationContext`, связанным с существующим контекстом.</span><span class="sxs-lookup"><span data-stu-id="71e26-192">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="71e26-193">Для `t:IssuedTokens` присоединения к исходящего `wscoor:CreateCoordinationContextResponse` сообщению должен быть создан новый заголовок.</span><span class="sxs-lookup"><span data-stu-id="71e26-193">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="71e26-194">Конфигурация привязки сообщений регистрации</span><span class="sxs-lookup"><span data-stu-id="71e26-194">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="71e26-195">B1231: WCF использует дуплексную привязку HTTPS (описано в [протоколах обмена сообщениями).](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="71e26-195">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="71e26-196">Сообщения запроса и ответа коррелируются с помощью WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="71e26-196">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="71e26-197">В разделе 8 спецификации WS-AtomicTransaction приводятся дополнительные сведения о корреляции и описание шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="71e26-197">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="71e26-198">R1232: Исходящие `wscoor:Register` сообщения `IssuedTokenOverTransport` должны использовать режим проверки подлинности, описанный в [Протоколах безопасности.](../../../../docs/framework/wcf/feature-details/security-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="71e26-198">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="71e26-199">Элемент `wsse:Timestamp` должен быть подписан `SecurityContextToken STx` с помощью выданного.</span><span class="sxs-lookup"><span data-stu-id="71e26-199">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="71e26-200">Эта подпись является доказательством владения маркером, связанным с конкретной транзакцией, и используется для проверки подлинности зачисления участника в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="71e26-200">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="71e26-201">Сообщение RegistrationResponse отправляется обратно по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="71e26-201">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="71e26-202">Конфигурация привязки протокола 2PC</span><span class="sxs-lookup"><span data-stu-id="71e26-202">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="71e26-203">WCF поддерживает односторонние (данные) сообщения через HTTPS.</span><span class="sxs-lookup"><span data-stu-id="71e26-203">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="71e26-204">Корреляция между сообщениями зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="71e26-204">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="71e26-205">B2131: Реализация должна `wsa:ReferenceParameters` поддерживаться, как описано в WS-Addressing для достижения корреляции 2PC сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="71e26-205">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="71e26-206">Обмен сообщениями приложений</span><span class="sxs-lookup"><span data-stu-id="71e26-206">Application Message Exchange</span></span>  
 <span data-ttu-id="71e26-207">Для сообщений, передаваемых между приложениями, приложения могут использовать любую привязку, если она удовлетворяет следующим требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="71e26-207">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="71e26-208">R2001: заголовок сообщений, передаваемых между приложениями, должен содержать заголовок `t:IssuedTokens` наряду с `CoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="71e26-208">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="71e26-209">R2002: необходимо обеспечение целостности и конфиденциальности `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="71e26-209">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="71e26-210">Заголовок `CoordinationContext` содержит `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="71e26-210">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="71e26-211">В то `xsd:AnyURI` время как определение позволяет использовать как абсолютные, так и относительные URI, WCF поддерживает только, `wscoor:Identifiers`которые являются абсолютными URIs.</span><span class="sxs-lookup"><span data-stu-id="71e26-211">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="71e26-212">`wscoor:Identifier` Если `wscoor:CoordinationContext` является относительным URI, неисправности будут возвращены из транзакционных служб WCF.</span><span class="sxs-lookup"><span data-stu-id="71e26-212">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="71e26-213">Примеры сообщений</span><span class="sxs-lookup"><span data-stu-id="71e26-213">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="71e26-214">Сообщения запроса и ответа CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="71e26-214">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="71e26-215">Следующие сообщения соответствуют шаблону "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="71e26-215">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="71e26-216">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="71e26-216">CreateCoordinationContext</span></span>  
  
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
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="71e26-217">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="71e26-217">CreateCoordinationContextResponse</span></span>  
  
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
  
### <a name="registration-messages"></a><span data-ttu-id="71e26-218">Сообщения регистрации</span><span class="sxs-lookup"><span data-stu-id="71e26-218">Registration Messages</span></span>  
 <span data-ttu-id="71e26-219">Следующие сообщения являются сообщениями регистрации.</span><span class="sxs-lookup"><span data-stu-id="71e26-219">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="71e26-220">Зарегистрировать</span><span class="sxs-lookup"><span data-stu-id="71e26-220">Register</span></span>  
  
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
  
#### <a name="register-response"></a><span data-ttu-id="71e26-221">Register Response</span><span class="sxs-lookup"><span data-stu-id="71e26-221">Register Response</span></span>  
  
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
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="71e26-222">Сообщения протокола двухфазной фиксации</span><span class="sxs-lookup"><span data-stu-id="71e26-222">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="71e26-223">Следующее сообщение относится к протоколу двухфазной фиксации (2PC).</span><span class="sxs-lookup"><span data-stu-id="71e26-223">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="71e26-224">Commit</span><span class="sxs-lookup"><span data-stu-id="71e26-224">Commit</span></span>  
  
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
  
### <a name="application-messages"></a><span data-ttu-id="71e26-225">Сообщения приложений</span><span class="sxs-lookup"><span data-stu-id="71e26-225">Application Messages</span></span>  
 <span data-ttu-id="71e26-226">Следующие сообщения являются сообщениями приложений.</span><span class="sxs-lookup"><span data-stu-id="71e26-226">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="71e26-227">Сообщение приложения - запрос</span><span class="sxs-lookup"><span data-stu-id="71e26-227">Application message-Request</span></span>  
  
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
