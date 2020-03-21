---
title: Протоколы транзакций
ms.date: 03/30/2017
ms.assetid: 2820b0ec-2f32-430c-b299-1f0e95e1f2dc
ms.openlocfilehash: 5ae8aa5112f737d3000e221d0a199c3ee36eac46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184370"
---
# <a name="transaction-protocols"></a><span data-ttu-id="c7bb2-102">Протоколы транзакций</span><span class="sxs-lookup"><span data-stu-id="c7bb2-102">Transaction Protocols</span></span>
<span data-ttu-id="c7bb2-103">Фонд связи Windows (WCF) реализует протоколы WS-Atomic Transaction и WS-Координация.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-103">Windows Communication Foundation (WCF) implements WS-Atomic Transaction and WS-Coordination protocols.</span></span>  
  
|<span data-ttu-id="c7bb2-104">Спецификация/документ</span><span class="sxs-lookup"><span data-stu-id="c7bb2-104">Specification/Document</span></span>|<span data-ttu-id="c7bb2-105">Версия</span><span class="sxs-lookup"><span data-stu-id="c7bb2-105">Version</span></span>|<span data-ttu-id="c7bb2-106">Ссылка</span><span class="sxs-lookup"><span data-stu-id="c7bb2-106">Link</span></span>|  
|-----------------------------|-------------|----------|  
|<span data-ttu-id="c7bb2-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="c7bb2-107">WS-Coordination</span></span>|<span data-ttu-id="c7bb2-108">1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-108">1.0</span></span><br /><br /> <span data-ttu-id="c7bb2-109">1,1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-109">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="c7bb2-110">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="c7bb2-110">WS-AtomicTransaction</span></span>|<span data-ttu-id="c7bb2-111">1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-111">1.0</span></span><br /><br /> <span data-ttu-id="c7bb2-112">1,1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-112">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
  
 <span data-ttu-id="c7bb2-113">Согласно этим спецификациям протоколов, требуется взаимодействие на двух уровнях: между приложениями и между диспетчерами транзакций (см. следующий рисунок).</span><span class="sxs-lookup"><span data-stu-id="c7bb2-113">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="c7bb2-114">В спецификациях подробно описываются форматы сообщений и обмен сообщениями для обоих уровней взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-114">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="c7bb2-115">При обмене между приложениями применяются определенные средства обеспечения безопасности, надежности и методы кодирования, как и при обычном обмене в пределах сообщения.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-115">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="c7bb2-116">Однако для успешного взаимодействия между диспетчерами транзакций требуется соглашение по конкретной привязке, поскольку она обычно не настраивается пользователем.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-116">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="c7bb2-117">В этом разделе описываются состав спецификации протокола WS-Atomic Transaction (WS-AT) со средствами безопасности, а также безопасная привязка, используемая для обмена данными между диспетчерами транзакций.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-117">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="c7bb2-118">Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination, включая IBM, IONA, Sun Microsystems и пр.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-118">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="c7bb2-119">Следующая цифра изображает совместимость между двумя менеджерами транзакций, менеджером транзакций 1 и менеджером транзакций 2, и двумя приложениями, Приложение 1 и Приложение 2:</span><span class="sxs-lookup"><span data-stu-id="c7bb2-119">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Скриншот, отображающие взаимодействие между менеджерами транзакций.](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="c7bb2-121">Рассмотрим типовой сценарий WS-Coordination/WS-Atomic Transaction с одним инициатором (I) и одним участником (P).</span><span class="sxs-lookup"><span data-stu-id="c7bb2-121">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="c7bb2-122">И инициатор, и участник имеют диспетчеры транзакций (ITM и PTM, соответственно).</span><span class="sxs-lookup"><span data-stu-id="c7bb2-122">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="c7bb2-123">Двухфазная фиксация обозначается в этом разделе как 2PC.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-123">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7bb2-124">1. СозданиеКоординацияКонтекст</span><span class="sxs-lookup"><span data-stu-id="c7bb2-124">1. CreateCoordinationContext</span></span>|<span data-ttu-id="c7bb2-125">12. Ответ на сообщение приложения</span><span class="sxs-lookup"><span data-stu-id="c7bb2-125">12. Application Message Response</span></span>|  
|<span data-ttu-id="c7bb2-126">2. СозданиеКоординационнаяКонтекстОтвет</span><span class="sxs-lookup"><span data-stu-id="c7bb2-126">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="c7bb2-127">13. Обязательство (Завершение)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-127">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="c7bb2-128">3. Регистрация (Завершение)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-128">3. Register (Completion)</span></span>|<span data-ttu-id="c7bb2-129">14. Подготовка (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-129">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="c7bb2-130">4. РегистрацияОтвет</span><span class="sxs-lookup"><span data-stu-id="c7bb2-130">4. RegisterResponse</span></span>|<span data-ttu-id="c7bb2-131">15. Подготовка (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-131">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="c7bb2-132">5. Сообщение приложения</span><span class="sxs-lookup"><span data-stu-id="c7bb2-132">5. Application Message</span></span>|<span data-ttu-id="c7bb2-133">16. Подготовлено (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-133">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="c7bb2-134">6. СозданиеКоординацияКонтекст с контекстом</span><span class="sxs-lookup"><span data-stu-id="c7bb2-134">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="c7bb2-135">17. Подготовлено (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-135">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="c7bb2-136">7. Регистрация (Долговечная)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-136">7. Register (Durable)</span></span>|<span data-ttu-id="c7bb2-137">18. Совершенные (Завершение)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-137">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="c7bb2-138">8. РегистрацияОтвет</span><span class="sxs-lookup"><span data-stu-id="c7bb2-138">8. RegisterResponse</span></span>|<span data-ttu-id="c7bb2-139">19. Обязательство (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-139">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="c7bb2-140">9. СозданиеКоординационнаяКонтекстОтвет</span><span class="sxs-lookup"><span data-stu-id="c7bb2-140">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="c7bb2-141">20. Обязательство (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-141">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="c7bb2-142">10. Регистрация (Долговечная)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-142">10. Register (Durable)</span></span>|<span data-ttu-id="c7bb2-143">21. Совершенные (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-143">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="c7bb2-144">11. РегистрацияОтвет</span><span class="sxs-lookup"><span data-stu-id="c7bb2-144">11. RegisterResponse</span></span>|<span data-ttu-id="c7bb2-145">22. Совершенные (2PC)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-145">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="c7bb2-146">В этом документе описываются состав спецификации протокола WS-AtomicTransaction со средствами безопасности, а также безопасная привязка, используемая для взаимодействия между диспетчерами транзакций.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-146">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="c7bb2-147">Подход, описанный в этом документе, успешно протестирован с другими реализациями протоколов WS-AT и WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-147">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="c7bb2-148">На рисунке и в таблице представлены четыре класса сообщений с точки зрения безопасности:</span><span class="sxs-lookup"><span data-stu-id="c7bb2-148">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="c7bb2-149">сообщения активации (CreateCoordinationContext и CreateCoordinationContextResponse);</span><span class="sxs-lookup"><span data-stu-id="c7bb2-149">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="c7bb2-150">сообщения регистрации (Register и RegisterResponse);</span><span class="sxs-lookup"><span data-stu-id="c7bb2-150">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="c7bb2-151">протокольные сообщения (Prepare, Rollback, Commit, Aborted и т. д.);</span><span class="sxs-lookup"><span data-stu-id="c7bb2-151">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="c7bb2-152">сообщения приложений.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-152">Application messages.</span></span>  
  
 <span data-ttu-id="c7bb2-153">Первые три класса сообщений считаются сообщениями диспетчера транзакций и их конфигурация привязки описывается в разделе "Обмен сообщениями приложений" ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-153">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="c7bb2-154">Четвертый класс сообщений - это сообщения, передаваемые между приложениями, которые описываются в разделе "Примеры сообщений" ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-154">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="c7bb2-155">В этом разделе описаны протокольные привязки, используемые для каждого из этих классов WCF.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-155">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="c7bb2-156">Во всем данном документе используются следующие пространства имен XML и связанные с ними префиксы.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-156">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="c7bb2-157">Prefix</span><span class="sxs-lookup"><span data-stu-id="c7bb2-157">Prefix</span></span>|<span data-ttu-id="c7bb2-158">Версия</span><span class="sxs-lookup"><span data-stu-id="c7bb2-158">Version</span></span>|<span data-ttu-id="c7bb2-159">Универсальный код ресурса (URI) пространства имен</span><span class="sxs-lookup"><span data-stu-id="c7bb2-159">Namespace URI</span></span>|  
|------------|-------------|-------------------|  
|<span data-ttu-id="c7bb2-160">s11</span><span class="sxs-lookup"><span data-stu-id="c7bb2-160">s11</span></span>||<https://schemas.xmlsoap.org/soap/envelope/>|  
|<span data-ttu-id="c7bb2-161">wsa</span><span class="sxs-lookup"><span data-stu-id="c7bb2-161">wsa</span></span>|<span data-ttu-id="c7bb2-162">До 1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-162">Pre-1.0</span></span><br /><br /> <span data-ttu-id="c7bb2-163">1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-163">1.0</span></span>|`http://www.w3.org/2004/08/addressing`<br /><br /> <https://www.w3.org/2005/08/addressing/>|  
|<span data-ttu-id="c7bb2-164">wscoor</span><span class="sxs-lookup"><span data-stu-id="c7bb2-164">wscoor</span></span>|<span data-ttu-id="c7bb2-165">1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-165">1.0</span></span><br /><br /> <span data-ttu-id="c7bb2-166">1,1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-166">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wscoor/><br /><br /> <https://docs.oasis-open.org/ws-tx/wscoor/2006/06>|  
|<span data-ttu-id="c7bb2-167">wsat</span><span class="sxs-lookup"><span data-stu-id="c7bb2-167">wsat</span></span>|<span data-ttu-id="c7bb2-168">1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-168">1.0</span></span><br /><br /> <span data-ttu-id="c7bb2-169">1,1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-169">1.1</span></span>|<http://schemas.xmlsoap.org/ws/2004/10/wsat/><br /><br /> <https://docs.oasis-open.org/ws-tx/wsat/2006/06>|  
|<span data-ttu-id="c7bb2-170">t</span><span class="sxs-lookup"><span data-stu-id="c7bb2-170">t</span></span>|<span data-ttu-id="c7bb2-171">До 1.3</span><span class="sxs-lookup"><span data-stu-id="c7bb2-171">Pre-1.3</span></span><br /><br /> <span data-ttu-id="c7bb2-172">1,3</span><span class="sxs-lookup"><span data-stu-id="c7bb2-172">1.3</span></span>|<http://schemas.xmlsoap.org/ws/2005/02/trust/><br /><br /> <https://docs.oasis-open.org/ws-sx/ws-trust/200512>|  
|<span data-ttu-id="c7bb2-173">o</span><span class="sxs-lookup"><span data-stu-id="c7bb2-173">o</span></span>||<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd>|  
|<span data-ttu-id="c7bb2-174">xsd</span><span class="sxs-lookup"><span data-stu-id="c7bb2-174">xsd</span></span>||<https://www.w3.org/2001/XMLSchema>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="c7bb2-175">Привязки диспетчеров транзакций</span><span class="sxs-lookup"><span data-stu-id="c7bb2-175">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="c7bb2-176">R1001: Менеджеры транзакций, участвующие в транзакции WS-AT 1.0, должны использовать SOAP 1.1 и WS-Addressing 2004/08 для WS-Atomic Transaction и WS-Координационных обменов сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-176">R1001: Transaction Managers participating in a WS-AT 1.0 transaction must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="c7bb2-177">R1002: для обмена сообщениями протоколов WS-Atomic Transaction и WS-Coordination диспетчеры транзакций, участвующие в транзакции по протоколу WS-AT 1.1, должны использовать SOAP 1.1 и WS-Addressing 2005/08.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-177">R1002: Transaction Managers participating in a WS-AT 1.1 transaction must use SOAP 1.1 and WS-Addressing 2005/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="c7bb2-178">Сообщения приложений не ограничиваются этими привязками и описываются ниже.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-178">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="c7bb2-179">Привязка HTTPS диспетчера транзакций</span><span class="sxs-lookup"><span data-stu-id="c7bb2-179">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="c7bb2-180">Для обеспечения безопасности и установления доверия между каждой парой "отправитель-получатель" в дереве транзакций привязка HTTPS диспетчера транзакций полагается только на механизм безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-180">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="c7bb2-181">Конфигурация транспорта HTTPS</span><span class="sxs-lookup"><span data-stu-id="c7bb2-181">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="c7bb2-182">Сертификаты X.509 используются для установления идентификации диспетчера транзакций.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-182">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="c7bb2-183">Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации:</span><span class="sxs-lookup"><span data-stu-id="c7bb2-183">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="c7bb2-184">R1111: сертификаты X.509, представляемые по линии связи, должны иметь имя субъекта, соответствующее полному доменному имени исходного компьютера;</span><span class="sxs-lookup"><span data-stu-id="c7bb2-184">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="c7bb2-185">B1112: для успешного выполнения проверок имени субъекта X.509 между каждой парой "отправитель-получатель" в системе должна работать служба DNS.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-185">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="c7bb2-186">Конфигурация привязки активации и регистрации</span><span class="sxs-lookup"><span data-stu-id="c7bb2-186">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="c7bb2-187">WCF требует привязки дуплекса запроса/ответа с корреляцией по HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-187">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="c7bb2-188">(Дополнительные сведения о корреляции и описание шаблонов обмена сообщениями "запрос-ответ" см. в разделе 8 спецификации WS-Atomic Transaction.)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-188">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="c7bb2-189">Конфигурация привязки протокола 2PC</span><span class="sxs-lookup"><span data-stu-id="c7bb2-189">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="c7bb2-190">WCF поддерживает односторонние (данные) сообщения через HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-190">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="c7bb2-191">Корреляция между сообщениями зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-191">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="c7bb2-192">B1131: Реализация должна `wsa:ReferenceParameters` поддерживаться, как описано в WS-Addressing для достижения корреляции 2PC сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-192">B1131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="c7bb2-193">Привязка безопасности диспетчера транзакций смешанного режима</span><span class="sxs-lookup"><span data-stu-id="c7bb2-193">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="c7bb2-194">Это альтернативная привязка (смешанного режима), которая для установления идентификации использует механизм безопасности транспорта в сочетании с моделью маркера, выдаваемого протоколом WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-194">This is an alternate (mixed mode) binding that uses transport security combined with the WS-Coordination Issued Token model for identity establishment purposes.</span></span> <span data-ttu-id="c7bb2-195">В двух привязках отличаются только элементы "Активация" и "Регистрация".</span><span class="sxs-lookup"><span data-stu-id="c7bb2-195">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="c7bb2-196">Конфигурация транспорта HTTPS</span><span class="sxs-lookup"><span data-stu-id="c7bb2-196">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="c7bb2-197">Сертификаты X.509 используются для установления идентификации диспетчера транзакций.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-197">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="c7bb2-198">Проверка подлинности клиента и сервера является обязательной, а авторизация клиента и сервера зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-198">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="c7bb2-199">Конфигурация привязки сообщений активации</span><span class="sxs-lookup"><span data-stu-id="c7bb2-199">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="c7bb2-200">Сообщения активации обычно не участвуют во взаимодействии, поскольку они, как правило, передаются между приложением и его локальным диспетчером транзакций.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-200">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="c7bb2-201">B1221: WCF использует дуплексную привязку HTTPS (описанную в [протоколах обмена сообщениями)](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)для сообщений активации.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-201">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="c7bb2-202">Сообщения запроса и ответа коррелируются с использованием протокола WS-Addressing 2004/08 в случае WS-AT 1.0 и протокола WS-Addressing 2005/08 в случае WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-202">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="c7bb2-203">В разделе 8 спецификации WS-Atomic Transaction приводятся дополнительные сведения о корреляции и шаблонах обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-203">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="c7bb2-204">R1222: при получении сообщения `CreateCoordinationContext` координатор должен выдать маркер `SecurityContextToken` со связанным с ним паролем `STx`.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-204">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="c7bb2-205">Этот маркер возвращается в заголовке `t:IssuedTokens` согласно спецификации WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-205">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="c7bb2-206">R1223: если активация происходит в пределах существующего контекста координации, в сообщении `t:IssuedTokens` должен передаваться заголовок `SecurityContextToken` с маркером `CreateCoordinationContext`, связанным с существующим контекстом.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-206">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="c7bb2-207">Для `t:IssuedTokens` присоединения к исходящего `wscoor:CreateCoordinationContextResponse` сообщению должен быть создан новый заголовок.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-207">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="c7bb2-208">Конфигурация привязки сообщений регистрации</span><span class="sxs-lookup"><span data-stu-id="c7bb2-208">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="c7bb2-209">B1231: WCF использует дуплексную привязку HTTPS (описано в [протоколах обмена сообщениями).](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-209">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="c7bb2-210">Сообщения запроса и ответа коррелируются с использованием протокола WS-Addressing 2004/08 в случае WS-AT 1.0 и протокола WS-Addressing 2005/08 в случае WS-AT 1.1.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-210">Request and Reply messages are correlated using WS-Addressing 2004/08 for WS-AT 1.0 and WS-Addressing 2005/08 for WS-AT 1.1.</span></span>  
  
 <span data-ttu-id="c7bb2-211">В разделе 8 спецификации WS-AtomicTransaction приводятся дополнительные сведения о корреляции и описание шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-211">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="c7bb2-212">R1232: Исходящие `wscoor:Register` сообщения `IssuedTokenOverTransport` должны использовать режим проверки подлинности, описанный в [Протоколах безопасности.](../../../../docs/framework/wcf/feature-details/security-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="c7bb2-212">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="c7bb2-213">Элемент `wsse:Timestamp` должен быть подписан `SecurityContextToken STx` с помощью выданного.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-213">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="c7bb2-214">Эта подпись является доказательством владения маркером, связанным с конкретной транзакцией, и используется для проверки подлинности зачисления участника в транзакцию.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-214">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="c7bb2-215">Сообщение RegistrationResponse отправляется обратно по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-215">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="c7bb2-216">Конфигурация привязки протокола 2PC</span><span class="sxs-lookup"><span data-stu-id="c7bb2-216">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="c7bb2-217">WCF поддерживает односторонние (данные) сообщения через HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-217">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="c7bb2-218">Корреляция между сообщениями зависит от реализации.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-218">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="c7bb2-219">B1241: Реализация должна `wsa:ReferenceParameters` поддерживаться, как описано в WS-Addressing для достижения корреляции 2PC сообщений WCF.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-219">B1241: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="c7bb2-220">Обмен сообщениями приложений</span><span class="sxs-lookup"><span data-stu-id="c7bb2-220">Application Message Exchange</span></span>  
 <span data-ttu-id="c7bb2-221">Для сообщений, передаваемых между приложениями, приложения могут использовать любую привязку, если она удовлетворяет следующим требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-221">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="c7bb2-222">R2001: заголовок сообщений, передаваемых между приложениями, должен содержать заголовок `t:IssuedTokens` наряду с `CoordinationContext`.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-222">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="c7bb2-223">R2002: необходимо обеспечение целостности и конфиденциальности `t:IssuedToken`.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-223">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="c7bb2-224">Заголовок `CoordinationContext` содержит `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-224">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="c7bb2-225">В то `xsd:AnyURI` время как определение позволяет использовать как абсолютные, так и относительные URI, WCF поддерживает только, `wscoor:Identifiers`которые являются абсолютными URIs.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-225">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="c7bb2-226">B2003: Если `wscoor:Identifier` `wscoor:CoordinationContext` является относительным URI, неисправности будут возвращены из транзакционных служб WCF.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-226">B2003: If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="c7bb2-227">Примеры сообщений</span><span class="sxs-lookup"><span data-stu-id="c7bb2-227">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="c7bb2-228">Сообщения запроса и ответа CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="c7bb2-228">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="c7bb2-229">Следующие сообщения соответствуют шаблону "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="c7bb2-229">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext-with-wscoor-10"></a><span data-ttu-id="c7bb2-230">СозданиеКоординационногоконтекста с помощью WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-230">CreateCoordinationContext with WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontext-with-wscoor-11"></a><span data-ttu-id="c7bb2-231">CreateCoordinationContext по WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-231">CreateCoordinationContext with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>
<s:Header>  
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContext</Action>  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-pre-13-and-wscoor-10"></a><span data-ttu-id="c7bb2-232">CreateCoordinationContextResponse по Trust версии до 1.3 и WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-232">CreateCoordinationContextResponse with Trust Pre-1.3 and WSCoor 1.0</span></span>  
  
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
  
#### <a name="createcoordinationcontextresponse-with-trust-13-and-wscoor-11"></a><span data-ttu-id="c7bb2-233">CreateCoordinationContextResponse по Trust 1.3 и WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-233">CreateCoordinationContextResponse with Trust 1.3 and WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<!-- Data below is shown in the clear for illustration purposes only. -->
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/CreateCoordinationContextResponse </a:Action>  
<a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
<a:To s:mustUnderstand="1">https://... </a:To>
<t:IssuedTokens>
<wst:RequestSecurityTokenResponse
xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"
xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"
xmlns:wst="http://docs.oasis-open.org/ws-sx/ws-trust/200512"  
xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
<wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
<wst:RequestedSecurityToken>
<wsc:SecurityContextToken>
<wssu:Identifier> http://fabrikam123.com/SCTi  
</wssu:Identifier>
</wsc:SecurityContextToken>
</wst:RequestedSecurityToken>
<wsp:AppliesTo> http://fabrikam123.com/CCi </wsp:AppliesTo>  
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
  Type="http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey">  
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
<wscoor:Identifier> http://fabrikam123.com/CCi  
</wscoor:Identifier>
<wscoor:Expires>...</wscoor:Expires>  
<wscoor:CoordinationType>...</wscoor:CoordinationType>  
<wscoor:RegistrationService>
<a:Address>https://...</a:Address>  
<a:ReferenceParameters> ...  
</a:ReferenceParameters>  
</wscoor:RegistrationService>
</wscoor:CoordinationContext>
</wscoor:CreateCoordinationContextResponse>
</s:Body>
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="c7bb2-234">Сообщения регистрации</span><span class="sxs-lookup"><span data-stu-id="c7bb2-234">Registration Messages</span></span>  
 <span data-ttu-id="c7bb2-235">Следующие сообщения являются сообщениями регистрации.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-235">The following messages are registration messages.</span></span>  
  
#### <a name="register-with-wscoor-10"></a><span data-ttu-id="c7bb2-236">Зарегистрируйтесь в WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-236">Register with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-with-wscoor-11"></a><span data-ttu-id="c7bb2-237">Register по WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-237">Register with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wscoor/2006/06/Register</a:Action>
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
<wssu:Identifier> http://fabrikam123.com/SCTi  
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
<ds:DigestMethod  
Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
<ds:DigestValue> alRzyhjLgoUOYoh8cx4n75eTcUk=  
</ds:DigestValue>
</ds:Reference>
</ds:SignedInfo>  
<ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=  
</ds:SignatureValue>  
<ds:KeyInfo>
<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
  <wsse:Reference URI="http://fabrikam123.com/SCTi"/>  
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
  
#### <a name="register-response-with-wscoor-10"></a><span data-ttu-id="c7bb2-238">Регистрация Ответ с WSCoor 1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-238">Register Response with WSCoor 1.0</span></span>  
  
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
  
#### <a name="register-response-with-wscoor-11"></a><span data-ttu-id="c7bb2-239">RegisterResponse по WSCoor 1.1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-239">Register Response with WSCoor 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action> http://docs.oasis-open.org/ws-tx/wscoor/2006/06/RegisterResponse  
</a:Action>
<a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
<a:RelatesTo> urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e </a:RelatesTo>  
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
<a:ReferenceParameters> ... </a:ReferenceParameters>  
</wscoor:CoordinatorProtocolService>
</wscoor:RegisterResponse>
</s:Body>
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="c7bb2-240">Сообщения протокола двухфазной фиксации</span><span class="sxs-lookup"><span data-stu-id="c7bb2-240">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="c7bb2-241">Следующее сообщение относится к протоколу двухфазной фиксации (2PC).</span><span class="sxs-lookup"><span data-stu-id="c7bb2-241">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit-with-wsat-10"></a><span data-ttu-id="c7bb2-242">Обязательство с WSAT 1.0</span><span class="sxs-lookup"><span data-stu-id="c7bb2-242">Commit with WSAT 1.0</span></span>  
  
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
  
#### <a name="commit-with-wsat-11"></a><span data-ttu-id="c7bb2-243">Commit по WSAT 1.1</span><span class="sxs-lookup"><span data-stu-id="c7bb2-243">Commit with WSAT 1.1</span></span>  
  
```xml  
<s:Envelope>  
<s:Header>
<a:Action>http://docs.oasis-open.org/ws-tx/wsat/2006/06</a:Action>  
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
  
### <a name="application-messages"></a><span data-ttu-id="c7bb2-244">Сообщения приложений</span><span class="sxs-lookup"><span data-stu-id="c7bb2-244">Application Messages</span></span>  
 <span data-ttu-id="c7bb2-245">Следующие сообщения являются сообщениями приложений.</span><span class="sxs-lookup"><span data-stu-id="c7bb2-245">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="c7bb2-246">Сообщение приложения - запрос</span><span class="sxs-lookup"><span data-stu-id="c7bb2-246">Application message-Request</span></span>  
  
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
