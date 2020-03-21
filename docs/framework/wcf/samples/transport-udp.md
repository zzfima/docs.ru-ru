---
title: 'Транспорт: UDP'
ms.date: 03/30/2017
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
ms.openlocfilehash: 3fd16ccd634b6875eae1e87547c35c6cba79c857
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143776"
---
# <a name="transport-udp"></a><span data-ttu-id="a0ca7-102">Транспорт: UDP</span><span class="sxs-lookup"><span data-stu-id="a0ca7-102">Transport: UDP</span></span>
<span data-ttu-id="a0ca7-103">Образец UDP Transport демонстрирует, как реализовать UDP unicast и multicast в качестве пользовательского Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a0ca7-103">The UDP Transport sample demonstrates how to implement UDP unicast and multicast as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="a0ca7-104">В выборке описывается рекомендуемая процедура создания пользовательского транспорта в WCF, с использованием платформы каналов и следуя передовой практике WCF.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-104">The sample describes the recommended procedure for creating a custom transport in WCF, by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="a0ca7-105">Для создания пользовательского транспорта выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-105">The steps to create a custom transport are as follows:</span></span>  
  
1. <span data-ttu-id="a0ca7-106">Решите, какой из [шаблонов обмена сообщениями](#MessageExchangePatterns) канала (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel или IReplyChannel) будет поддерживать ваш ChannelFactory и ChannelListener.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-106">Decide which of the channel [Message Exchange Patterns](#MessageExchangePatterns) (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel, or IReplyChannel) your ChannelFactory and ChannelListener will support.</span></span> <span data-ttu-id="a0ca7-107">Затем решите, поддерживать ли связанные с сеансами разновидности указанных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-107">Then decide whether you will support the sessionful variations of these interfaces.</span></span>  
  
2. <span data-ttu-id="a0ca7-108">Создайте фабрику и прослушиватель каналов, которые поддерживают выбранный шаблон обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-108">Create a channel factory and listener that support your Message Exchange Pattern.</span></span>  
  
3. <span data-ttu-id="a0ca7-109">Убедитесь, что все исключения, связанные с сетью, нормализованы в соответствующий класс, унаследованный от <xref:System.ServiceModel.CommunicationException>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
4. <span data-ttu-id="a0ca7-110">Добавьте [ \<связывающий>](../../configure-apps/file-schema/wcf/bindings.md) элемент, который добавляет пользовательский перенос в стек канала.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-110">Add a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="a0ca7-111">Для получения дополнительной информации [см.](#AddingABindingElement)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-111">For more information, see [Adding a Binding Element](#AddingABindingElement).</span></span>  
  
5. <span data-ttu-id="a0ca7-112">Добавьте раздел расширения элементов привязки, чтобы представить новый элемент привязки системе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-112">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
6. <span data-ttu-id="a0ca7-113">Добавьте расширения метаданных, чтобы сообщить о возможностях в другие конечные точки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-113">Add metadata extensions to communicate capabilities to other endpoints.</span></span>  
  
7. <span data-ttu-id="a0ca7-114">Добавьте привязку, которая предварительно настраивает стек элементов привязки в соответствии с четко определенным профилем.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-114">Add a binding that pre-configures a stack of binding elements according to a well-defined profile.</span></span> <span data-ttu-id="a0ca7-115">Для получения дополнительной информации [см.](#AddingAStandardBinding)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-115">For more information, see [Adding a Standard Binding](#AddingAStandardBinding).</span></span>  
  
8. <span data-ttu-id="a0ca7-116">Добавьте раздел привязки и элемент конфигурации привязки, чтобы представить привязку системе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-116">Add a binding section and binding configuration element to expose the binding to the configuration system.</span></span> <span data-ttu-id="a0ca7-117">Для получения дополнительной информации [см.](#AddingConfigurationSupport)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-117">For more information, see [Adding Configuration Support](#AddingConfigurationSupport).</span></span>  
  
<a name="MessageExchangePatterns"></a>
## <a name="message-exchange-patterns"></a><span data-ttu-id="a0ca7-118">Шаблоны обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="a0ca7-118">Message Exchange Patterns</span></span>  
 <span data-ttu-id="a0ca7-119">При создании пользовательского транспорта в первую очередь решите, какие шаблоны обмена сообщениями требуются для транспорта.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-119">The first step in writing a custom transport is to decide which Message Exchange Patterns (MEPs) are required for the transport.</span></span> <span data-ttu-id="a0ca7-120">Можно выбирать из трех шаблонов обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-120">There are three MEPs to choose from:</span></span>  
  
- <span data-ttu-id="a0ca7-121">Датаграмма (IInputChannel/IOutputChannel)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-121">Datagram (IInputChannel/IOutputChannel)</span></span>  
  
     <span data-ttu-id="a0ca7-122">При использовании шаблона обмена сообщениями "датаграмма" клиент отправляет сообщения, используя принцип "отправить и забыть".</span><span class="sxs-lookup"><span data-stu-id="a0ca7-122">When using a datagram MEP, a client sends a message using a "fire and forget" exchange.</span></span> <span data-ttu-id="a0ca7-123">В этом случае требуется внешнее подтверждение успешной доставки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-123">A fire and forget exchange is one that requires out-of-band confirmation of successful delivery.</span></span> <span data-ttu-id="a0ca7-124">Сообщение может быть потеряно при передаче и может не достичь службы.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-124">The message might be lost in transit and never reach the service.</span></span> <span data-ttu-id="a0ca7-125">Если операция отправки успешно выполняется на стороне клиента, это не гарантирует, что удаленная конечная точка получит сообщение.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-125">If the send operation completes successfully at the client end, it does not guarantee that the remote endpoint has received the message.</span></span> <span data-ttu-id="a0ca7-126">Датаграмма - фундаментальный элемент обмена сообщениями, на основе которого можно строить собственные протоколы, в том числе надежные и безопасные.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-126">The datagram is a fundamental building block for messaging, as you can build your own protocols on top of it—including reliable protocols and secure protocols.</span></span> <span data-ttu-id="a0ca7-127">Каналы датаграмм клиентов реализуют интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>, а каналы датаграмм служб - интерфейс <xref:System.ServiceModel.Channels.IInputChannel>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-127">Client datagram channels implement the <xref:System.ServiceModel.Channels.IOutputChannel> interface and service datagram channels implement the <xref:System.ServiceModel.Channels.IInputChannel> interface.</span></span>  
  
- <span data-ttu-id="a0ca7-128">Запрос-ответ (IRequestChannel/IReplyChannel)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-128">Request-Response (IRequestChannel/IReplyChannel)</span></span>  
  
     <span data-ttu-id="a0ca7-129">При использовании этого шаблона происходит отправка сообщения и получение ответа.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-129">In this MEP, a message is sent, and a reply is received.</span></span> <span data-ttu-id="a0ca7-130">Шаблон состоит из пар «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="a0ca7-130">The pattern consists of request-response pairs.</span></span> <span data-ttu-id="a0ca7-131">Примеры вызовов "запрос-ответ" - удаленные вызовы процедур и запросы GET браузера.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-131">Examples of request-response calls are remote procedure calls (RPC) and browser GETs.</span></span> <span data-ttu-id="a0ca7-132">Этот шаблон также называют полудуплексным.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-132">This pattern is also known as Half-Duplex.</span></span> <span data-ttu-id="a0ca7-133">При использовании этого шаблона обмена сообщениями каналы клиентов реализуют интерфейс <xref:System.ServiceModel.Channels.IRequestChannel>, а каналы служб - интерфейс <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-133">In this MEP, client channels implement <xref:System.ServiceModel.Channels.IRequestChannel> and service channels implement <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span>  
  
- <span data-ttu-id="a0ca7-134">Дуплекс (IDuplexChannel)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-134">Duplex (IDuplexChannel)</span></span>  
  
     <span data-ttu-id="a0ca7-135">Дуплексный шаблон обмена сообщениями позволяет клиенту отправлять произвольное количество сообщений и принимать их в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-135">The duplex MEP allows an arbitrary number of messages to be sent by a client and received in any order.</span></span> <span data-ttu-id="a0ca7-136">Применение дуплексного шаблона похоже на разговор по телефону, когда каждое произносимое слово является сообщением.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-136">The duplex MEP is like a phone conversation, where each word being spoken is a message.</span></span> <span data-ttu-id="a0ca7-137">Поскольку в данном случае принимать и отправлять сообщения могут обе стороны, каналы клиента и службы реализуют интерфейс <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-137">Because both sides can send and receive in this MEP, the interface implemented by the client and service channels is <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
 <span data-ttu-id="a0ca7-138">Каждый из этих шаблонов обмена сообщениями также поддерживает сеансы.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-138">Each of these MEPs can also support sessions.</span></span> <span data-ttu-id="a0ca7-139">Канал, поддерживающий сеансы, содержит функции для согласования всех сообщений, отправляемых и принимаемых через канал.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-139">The added functionality provided by a session-aware channel is that it correlates all messages sent and received on a channel.</span></span> <span data-ttu-id="a0ca7-140">Шаблон "запрос-ответ" является отдельным сеансом из двух сообщений, поскольку запрос и ответ связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-140">The Request-Response pattern is a stand-alone two-message session, as the request and reply are correlated.</span></span> <span data-ttu-id="a0ca7-141">В отличие от него в поддерживающем сеансы шаблоне "запрос-ответ" предполагается, что все пары "запрос-ответ" в канале связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-141">In contrast, the Request-Response pattern that supports sessions implies that all request/response pairs on that channel are correlated with each other.</span></span> <span data-ttu-id="a0ca7-142">Таким образом, можно выбирать один из шести шаблонов: датаграмма, "запрос-ответ", дуплекс, датаграмма с поддержкой сеансов, "запрос-ответ" с поддержкой сеансов и дуплекс с поддержкой сеансов.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-142">This gives you a total of six MEPs—Datagram, Request-Response, Duplex, Datagram with sessions, Request-Response with sessions, and Duplex with sessions—to choose from.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0ca7-143">Для транспорта по протоколу UDP единственным поддерживаемым шаблоном обмена сообщениями является датаграмма, поскольку структура протокола UDP основана на принципе "отправить и забыть".</span><span class="sxs-lookup"><span data-stu-id="a0ca7-143">For the UDP transport, the only MEP that is supported is Datagram, because UDP is inherently a "fire and forget" protocol.</span></span>  
  
### <a name="the-icommunicationobject-and-the-wcf-object-lifecycle"></a><span data-ttu-id="a0ca7-144">Жизненный цикл ICommunicationObject и объектов WCF</span><span class="sxs-lookup"><span data-stu-id="a0ca7-144">The ICommunicationObject and the WCF object lifecycle</span></span>  
 <span data-ttu-id="a0ca7-145">WCF имеет общую государственную машину, которая используется <xref:System.ServiceModel.Channels.IChannel> <xref:System.ServiceModel.Channels.IChannelFactory>для <xref:System.ServiceModel.Channels.IChannelListener> управления жизненным циклом таких объектов, как , и которые используются для связи.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-145">WCF has a common state machine that is used for managing the lifecycle of objects like <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory>, and <xref:System.ServiceModel.Channels.IChannelListener> that are used for communication.</span></span> <span data-ttu-id="a0ca7-146">Эти объекты взаимодействий могут находиться в пяти состояниях.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-146">There are five states in which these communication objects can exist.</span></span> <span data-ttu-id="a0ca7-147">Эти состояния, приведенные ниже, представлены перечислением <xref:System.ServiceModel.CommunicationState>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-147">These states are represented by the <xref:System.ServiceModel.CommunicationState> enumeration, and are as follows:</span></span>  
  
- <span data-ttu-id="a0ca7-148">Создано: Это состояние, <xref:System.ServiceModel.ICommunicationObject> когда он впервые мгновенно.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-148">Created: This is the state of a <xref:System.ServiceModel.ICommunicationObject> when it is first instantiated.</span></span> <span data-ttu-id="a0ca7-149">Ввод и вывод в этом состоянии не происходит.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-149">No input/output (I/O) occurs in this state.</span></span>  
  
- <span data-ttu-id="a0ca7-150">Открытие: Объекты переходят <xref:System.ServiceModel.ICommunicationObject.Open%2A> в это состояние при вызове.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-150">Opening: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="a0ca7-151">В этот момент свойства перестают быть изменяемыми, и могут начинаться ввод и вывод.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-151">At this point properties are made immutable, and input/output can begin.</span></span> <span data-ttu-id="a0ca7-152">Переход в это состояние возможен только из состояния Created.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-152">This transition is valid only from the Created state.</span></span>  
  
- <span data-ttu-id="a0ca7-153">Opened: в это состояние объекты переходят по окончании процесса открытия.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-153">Opened: Objects transition to this state when the open process completes.</span></span> <span data-ttu-id="a0ca7-154">Переход в это состояние возможен только из состояния Opening.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-154">This transition is valid only from the Opening state.</span></span> <span data-ttu-id="a0ca7-155">С этого момента объект полностью пригоден для передачи сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-155">At this point, the object is fully usable for transfer.</span></span>  
  
- <span data-ttu-id="a0ca7-156">Закрытие: Объекты переходят <xref:System.ServiceModel.ICommunicationObject.Close%2A> в это состояние, когда требуется изящное завершение работы.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-156">Closing: Objects transition to this state when <xref:System.ServiceModel.ICommunicationObject.Close%2A> is called for a graceful shutdown.</span></span> <span data-ttu-id="a0ca7-157">Переход в это состояние возможен только из состояния Opened.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-157">This transition is valid only from the Opened state.</span></span>  
  
- <span data-ttu-id="a0ca7-158">Closed: в состоянии Closed объекты использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-158">Closed: In the Closed state objects are no longer usable.</span></span> <span data-ttu-id="a0ca7-159">В общем случае большинство конфигураций доступны для изучения, но никакие взаимодействия происходить не могут.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-159">In general, most configuration is still accessible for inspection, but no communication can occur.</span></span> <span data-ttu-id="a0ca7-160">Это состояние равнозначно удалению.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-160">This state is equivalent to being disposed.</span></span>  
  
- <span data-ttu-id="a0ca7-161">Faulted: в состоянии Faulted объекты доступны для изучения, но их нельзя использовать.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-161">Faulted: In the Faulted state, objects are accessible to inspection but no longer usable.</span></span> <span data-ttu-id="a0ca7-162">Объекты переходят в это состояние при возникновении неустранимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-162">When a non-recoverable error occurs, the object transitions into this state.</span></span> <span data-ttu-id="a0ca7-163">Единственным допустимым переходом из `Closed` этого состояния является состояние.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-163">The only valid transition from this state is into the `Closed` state.</span></span>  
  
 <span data-ttu-id="a0ca7-164">Есть события, возникающие при каждом изменении состояния.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-164">There are events that fire for each state transition.</span></span> <span data-ttu-id="a0ca7-165">Метод <xref:System.ServiceModel.ICommunicationObject.Abort%2A> может быть вызван в любое время и приводит к немедленному переходу объекта из текущего состояния в закрытое состояние.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-165">The <xref:System.ServiceModel.ICommunicationObject.Abort%2A> method can be called at any time, and causes the object to transition immediately from its current state into the Closed state.</span></span> <span data-ttu-id="a0ca7-166">Вызов <xref:System.ServiceModel.ICommunicationObject.Abort%2A> прекращает любую незаконченную работу.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-166">Calling <xref:System.ServiceModel.ICommunicationObject.Abort%2A> terminates any unfinished work.</span></span>  
  
<a name="ChannelAndChannelListener"></a>
## <a name="channel-factory-and-channel-listener"></a><span data-ttu-id="a0ca7-167">Фабрика каналов и прослушиватель каналов</span><span class="sxs-lookup"><span data-stu-id="a0ca7-167">Channel Factory and Channel Listener</span></span>  
 <span data-ttu-id="a0ca7-168">Следующий этап создания пользовательского транспорта - реализация <xref:System.ServiceModel.Channels.IChannelFactory> для каналов клиентов и <xref:System.ServiceModel.Channels.IChannelListener> для каналов служб.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-168">The next step in writing a custom transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span> <span data-ttu-id="a0ca7-169">Уровень канала использует шаблон фабрики для создания каналов.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-169">The channel layer uses a factory pattern for constructing channels.</span></span> <span data-ttu-id="a0ca7-170">WCF предоставляет помощников базового класса для этого процесса.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-170">WCF provides base class helpers for this process.</span></span>  
  
- <span data-ttu-id="a0ca7-171">Класс <xref:System.ServiceModel.Channels.CommunicationObject> реализует интерфейс <xref:System.ServiceModel.ICommunicationObject> и принудительно создает конечный автомат, описанный ранее на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-171">The <xref:System.ServiceModel.Channels.CommunicationObject> class implements <xref:System.ServiceModel.ICommunicationObject> and enforces the state machine previously described in Step 2.</span></span>

- <span data-ttu-id="a0ca7-172">Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> реализует <xref:System.ServiceModel.Channels.CommunicationObject> и обеспечивает единый <xref:System.ServiceModel.Channels.ChannelFactoryBase> базовый класс для и <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-172">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class implements <xref:System.ServiceModel.Channels.CommunicationObject> and provides a unified base class for <xref:System.ServiceModel.Channels.ChannelFactoryBase> and <xref:System.ServiceModel.Channels.ChannelListenerBase>.</span></span> <span data-ttu-id="a0ca7-173">Класс <xref:System.ServiceModel.Channels.ChannelManagerBase> работает совместно с классом <xref:System.ServiceModel.Channels.ChannelBase> - базовым классом, реализующим интерфейс <xref:System.ServiceModel.Channels.IChannel>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-173">The <xref:System.ServiceModel.Channels.ChannelManagerBase> class works in conjunction with <xref:System.ServiceModel.Channels.ChannelBase>, which is a base class that implements <xref:System.ServiceModel.Channels.IChannel>.</span></span>  
  
- <span data-ttu-id="a0ca7-174">Класс <xref:System.ServiceModel.Channels.ChannelFactoryBase> реализует <xref:System.ServiceModel.Channels.ChannelManagerBase> и <xref:System.ServiceModel.Channels.IChannelFactory> объединяет `CreateChannel` перегрузки в `OnCreateChannel` один абстрактный метод.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-174">The <xref:System.ServiceModel.Channels.ChannelFactoryBase> class implements <xref:System.ServiceModel.Channels.ChannelManagerBase> and <xref:System.ServiceModel.Channels.IChannelFactory> and consolidates the `CreateChannel` overloads into one `OnCreateChannel` abstract method.</span></span>  
  
- <span data-ttu-id="a0ca7-175">Класс <xref:System.ServiceModel.Channels.ChannelListenerBase> реализует <xref:System.ServiceModel.Channels.IChannelListener>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-175">The <xref:System.ServiceModel.Channels.ChannelListenerBase> class implements <xref:System.ServiceModel.Channels.IChannelListener>.</span></span> <span data-ttu-id="a0ca7-176">Он отвечает за базовое управление состоянием.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-176">It takes care of basic state management.</span></span>  
  
 <span data-ttu-id="a0ca7-177">В этом образце реализация фабрики содержится в UdpChannelFactory.cs, а реализация прослушивателя содержится в UdpChannelListener.cs.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-177">In this sample, the factory implementation is contained in UdpChannelFactory.cs and the listener implementation is contained in UdpChannelListener.cs.</span></span> <span data-ttu-id="a0ca7-178">Реализации <xref:System.ServiceModel.Channels.IChannel> находятся в UdpOutputChannel.cs и UdpInputChannel.cs.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-178">The <xref:System.ServiceModel.Channels.IChannel> implementations are in UdpOutputChannel.cs and UdpInputChannel.cs.</span></span>  
  
### <a name="the-udp-channel-factory"></a><span data-ttu-id="a0ca7-179">Фабрика канала UDP</span><span class="sxs-lookup"><span data-stu-id="a0ca7-179">The UDP Channel Factory</span></span>  
 <span data-ttu-id="a0ca7-180">Фабрика`UdpChannelFactory` наследуется от класса <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-180">The `UdpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>.</span></span> <span data-ttu-id="a0ca7-181">В образце переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> для обеспечения доступа к версии сообщения кодировщика сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-181">The sample overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> to provide access to the message version of the message encoder.</span></span> <span data-ttu-id="a0ca7-182">Также переопределяется метод <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A>, позволяющий убрать созданный экземпляр класса <xref:System.ServiceModel.Channels.BufferManager> при переходе конечного автомата в другое состояние.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-182">The sample also overrides <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> so that we can tear down our instance of <xref:System.ServiceModel.Channels.BufferManager> when the state machine transitions.</span></span>  
  
#### <a name="the-udp-output-channel"></a><span data-ttu-id="a0ca7-183">Выходной канал UDP</span><span class="sxs-lookup"><span data-stu-id="a0ca7-183">The UDP Output Channel</span></span>  
 <span data-ttu-id="a0ca7-184">Класс`UdpOutputChannel` реализует интерфейс <xref:System.ServiceModel.Channels.IOutputChannel>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-184">The `UdpOutputChannel` implements <xref:System.ServiceModel.Channels.IOutputChannel>.</span></span> <span data-ttu-id="a0ca7-185">Конструктор проверяет аргументы и создает целевой объект <xref:System.Net.EndPoint> на основании переданного ему адреса <xref:System.ServiceModel.EndpointAddress>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-185">The constructor validates the arguments and constructs a destination <xref:System.Net.EndPoint> object based on the <xref:System.ServiceModel.EndpointAddress> that is passed in.</span></span>  
  
```csharp
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
```  
  
 <span data-ttu-id="a0ca7-186">Канал может быть закрыт правильно или неправильно.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-186">The channel can be closed gracefully or ungracefully.</span></span> <span data-ttu-id="a0ca7-187">При верном закрытии канала сокет закрывается и вызывается метод `OnClose` базового класса.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-187">If the channel is closed gracefully the socket is closed and a call is made to the base class `OnClose` method.</span></span> <span data-ttu-id="a0ca7-188">Если при этом создается исключение, инфраструктура вызывает метод `Abort`, чтоб обеспечить очистку канала.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-188">If this throws an exception, the infrastructure calls `Abort` to ensure the channel is cleaned up.</span></span>  
  
```csharp
this.socket.Close(0);  
```  
  
 <span data-ttu-id="a0ca7-189">Затем мы `Send()` `BeginSend()` / `EndSend()`реализуем и .</span><span class="sxs-lookup"><span data-stu-id="a0ca7-189">We then implement `Send()` and `BeginSend()`/`EndSend()`.</span></span> <span data-ttu-id="a0ca7-190">Реализация делится на две принципиальные части.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-190">This breaks down into two main sections.</span></span> <span data-ttu-id="a0ca7-191">Сначала сообщение сериализуется в байтовый массив.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-191">First we serialize the message into a byte array.</span></span>  
  
```csharp
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 <span data-ttu-id="a0ca7-192">Затем получившиеся данные отправляются по сети.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-192">Then we send the resulting data on the wire.</span></span>  
  
```csharp
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### <a name="the-udpchannellistener"></a><span data-ttu-id="a0ca7-193">Класс UdpChannelListener</span><span class="sxs-lookup"><span data-stu-id="a0ca7-193">The UdpChannelListener</span></span>  
 <span data-ttu-id="a0ca7-194">Тот, `UdpChannelListener` который реализует образец, <xref:System.ServiceModel.Channels.ChannelListenerBase> происходит от класса.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-194">The `UdpChannelListener` that the sample implements derives from the <xref:System.ServiceModel.Channels.ChannelListenerBase> class.</span></span> <span data-ttu-id="a0ca7-195">Он использует один UDP-сокет для приема датаграмм.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-195">It uses a single UDP socket to receive datagrams.</span></span> <span data-ttu-id="a0ca7-196">Метод `OnOpen` принимает данные через UDP-сокет в асинхронном цикле.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-196">The `OnOpen` method receives data using the UDP socket in an asynchronous loop.</span></span> <span data-ttu-id="a0ca7-197">Затем данные преобразуются в сообщения с помощью системы кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-197">The data are then converted into messages using the Message Encoding Framework.</span></span>  
  
```csharp
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 <span data-ttu-id="a0ca7-198">Поскольку один канал датаграмм представляет сообщения, приходящие из нескольких источников, `UdpChannelListener` - одноэлементный прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-198">Because the same datagram channel represents messages that arrive from a number of sources, the `UdpChannelListener` is a singleton listener.</span></span> <span data-ttu-id="a0ca7-199">Существует, в лучшем случае, один активный <xref:System.ServiceModel.Channels.IChannel> связанный с этим слушателем в то время.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-199">There is, at most, one active <xref:System.ServiceModel.Channels.IChannel> associated with this listener at a time.</span></span> <span data-ttu-id="a0ca7-200">В образце создается новый экземпляр только в том случае, если канал, возвращенный методом `AcceptChannel`, был впоследствии освобожден.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-200">The sample generates another one only if a channel that is returned by the `AcceptChannel` method is subsequently disposed.</span></span> <span data-ttu-id="a0ca7-201">Когда сообщение принято, оно ставится в очередь в этот одноэлементный канал.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-201">When a message is received, it is enqueued into this singleton channel.</span></span>  
  
#### <a name="udpinputchannel"></a><span data-ttu-id="a0ca7-202">UdpInputChannel</span><span class="sxs-lookup"><span data-stu-id="a0ca7-202">UdpInputChannel</span></span>  
 <span data-ttu-id="a0ca7-203">Класс `UdpInputChannel` реализует `IInputChannel`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-203">The `UdpInputChannel` class implements `IInputChannel`.</span></span> <span data-ttu-id="a0ca7-204">Он состоит из очереди входящих сообщений, которая заполняется сокетом прослушивателя `UdpChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-204">It consists of a queue of incoming messages that is populated by the `UdpChannelListener`'s socket.</span></span> <span data-ttu-id="a0ca7-205">Эти сообщения разогнаны `IInputChannel.Receive` методом.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-205">These messages are dequeued by the `IInputChannel.Receive` method.</span></span>  
  
<a name="AddingABindingElement"></a>
## <a name="adding-a-binding-element"></a><span data-ttu-id="a0ca7-206">Добавление элемента привязки</span><span class="sxs-lookup"><span data-stu-id="a0ca7-206">Adding a Binding Element</span></span>  
 <span data-ttu-id="a0ca7-207">После создания фабрики и каналы нужно предоставить среде выполнения ServiceModel через привязку.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-207">Now that the factories and channels are built, we must expose them to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="a0ca7-208">Привязка - это коллекция элементов привязки, представляющая стек связи для адреса службы.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-208">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="a0ca7-209">Каждый элемент в стеке представлен [ \<связывающим элементом>.](../../configure-apps/file-schema/wcf/bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-209">Each element in the stack is represented by a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
 <span data-ttu-id="a0ca7-210">В этом примере в качестве элемента привязки выступает элемент `UdpTransportBindingElement`, являющийся производным элемента <xref:System.ServiceModel.Channels.TransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-210">In the sample, the binding element is `UdpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="a0ca7-211">Он переопределяет следующие методы создания фабрик, связанных с привязкой.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-211">It overrides the following methods to build the factories associated with our binding.</span></span>  
  
```csharp
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 <span data-ttu-id="a0ca7-212">Он также содержит члены для клонирования элемента `BindingElement` и возврата схемы (soap.udp).</span><span class="sxs-lookup"><span data-stu-id="a0ca7-212">It also contains members for cloning the `BindingElement` and returning our scheme (soap.udp).</span></span>  
  
## <a name="adding-metadata-support-for-a-transport-binding-element"></a><span data-ttu-id="a0ca7-213">Добавление поддержки метаданных для элемента привязки транспорта</span><span class="sxs-lookup"><span data-stu-id="a0ca7-213">Adding Metadata Support for a Transport Binding Element</span></span>  
 <span data-ttu-id="a0ca7-214">Для интеграции в систему метаданных транспорт должен поддерживать как импорт, так и экспорт политики.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-214">To integrate our transport into the metadata system, we must support both the import and export of policy.</span></span> <span data-ttu-id="a0ca7-215">Это позволяет нам генерировать клиентов нашей привязки через [ServiceModel Metadata Утилита инструмент (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="a0ca7-215">This allows us to generate clients of our binding through the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="a0ca7-216">Добавление поддержки WSDL</span><span class="sxs-lookup"><span data-stu-id="a0ca7-216">Adding WSDL Support</span></span>  
 <span data-ttu-id="a0ca7-217">За экспорт и импорт адресов в метаданных отвечает элемент привязки транспорта.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-217">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="a0ca7-218">При использовании привязки протокола SOAP элемент привязки транспорта должен также экспортировать в метаданных правильный URI (универсальный код ресурса) транспорта.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-218">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="a0ca7-219">Экспорт WSDL</span><span class="sxs-lookup"><span data-stu-id="a0ca7-219">WSDL Export</span></span>  
 <span data-ttu-id="a0ca7-220">Для экспорта адресов элемент `UdpTransportBindingElement` реализует интерфейс `IWsdlExportExtension`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-220">To export addressing information the `UdpTransportBindingElement` implements the `IWsdlExportExtension` interface.</span></span> <span data-ttu-id="a0ca7-221">Метод `ExportEndpoint` добавляет правильную информацию адресации в порт WSDL.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-221">The `ExportEndpoint` method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="a0ca7-222">Реализация метода `UdpTransportBindingElement` в элементе `ExportEndpoint` также экспортирует URI транспорта, когда конечная точка использует привязку SOAP.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-222">The `UdpTransportBindingElement` implementation of the `ExportEndpoint` method also exports a transport URI when the endpoint uses a SOAP binding.</span></span>  
  
```csharp
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="a0ca7-223">Импорт WSDL</span><span class="sxs-lookup"><span data-stu-id="a0ca7-223">WSDL Import</span></span>  
 <span data-ttu-id="a0ca7-224">Для расширения системы импорта WSDL для обработки импорта адресов нужно добавить в файл конфигурации средства Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-224">To extend the WSDL import system to handle importing the addresses, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a0ca7-225">При запуске Svcutil.exe существует два варианта обеспечить загрузку программой расширений импорта WSDL:</span><span class="sxs-lookup"><span data-stu-id="a0ca7-225">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="a0ca7-226">Точка Svcutil.exe к нашему файлу конфигурации с\<помощью /SvcutilConfig: файл>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-226">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="a0ca7-227">добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-227">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="a0ca7-228">Тип `UdpBindingElementImporter` реализует `IWsdlImportExtension` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-228">The `UdpBindingElementImporter` type implements the `IWsdlImportExtension` interface.</span></span> <span data-ttu-id="a0ca7-229">Метод `ImportEndpoint` импортирует адрес из порта WSDL.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-229">The `ImportEndpoint` method imports the address from the WSDL port.</span></span>  
  
```csharp
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="a0ca7-230">Добавление поддержки политик</span><span class="sxs-lookup"><span data-stu-id="a0ca7-230">Adding Policy Support</span></span>  
 <span data-ttu-id="a0ca7-231">Пользовательский элемент привязки может экспортировать утверждения политики в привязке WSDL для конечной точки службы, чтобы показать возможности этого элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-231">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="a0ca7-232">Экспорт политики</span><span class="sxs-lookup"><span data-stu-id="a0ca7-232">Policy Export</span></span>  
 <span data-ttu-id="a0ca7-233">Тип `UdpTransportBindingElement` реализует `IPolicyExportExtension` для добавления поддержки экспортной политики.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-233">The `UdpTransportBindingElement` type implements `IPolicyExportExtension` to add support for exporting policy.</span></span> <span data-ttu-id="a0ca7-234">В результате класс `System.ServiceModel.MetadataExporter` включает элемент `UdpTransportBindingElement` при формировании политики для любой привязки, в которую он входит.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-234">As a result, `System.ServiceModel.MetadataExporter` includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="a0ca7-235">В методе `IPolicyExportExtension.ExportPolicy` добавляется утверждение для UDP и еще одно утверждение, если используется режим многоадресной рассылки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-235">In `IPolicyExportExtension.ExportPolicy`, we add an assertion for UDP and another assertion if we are in multicast mode.</span></span> <span data-ttu-id="a0ca7-236">Это связано с тем, что режим многоадресной рассылки влияет на построение стека связи и, следовательно, должен быть согласован обеими сторонами.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-236">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
```csharp
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(
        UdpPolicyStrings.Prefix,
        UdpPolicyStrings.MulticastAssertion,
        UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 <span data-ttu-id="a0ca7-237">Поскольку пользовательские элементы привязки транспорта отвечают за обработку адресов, реализация `IPolicyExportExtension` в элементе `UdpTransportBindingElement` должна также обрабатывать экспорт соответствующих утверждений политики WS-Addressing для указания используемой версии WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-237">Because custom transport binding elements are responsible for handling addressing, the `IPolicyExportExtension` implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="a0ca7-238">Импорт политики</span><span class="sxs-lookup"><span data-stu-id="a0ca7-238">Policy Import</span></span>  
 <span data-ttu-id="a0ca7-239">Чтобы расширить систему импорта политик, нужно добавить в файл конфигурации Svcutil.exe следующую конфигурацию, как показано в файле Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-239">To extend the Policy Import system, we must add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a0ca7-240">Затем мы реализуем интерфейс `IPolicyImporterExtension` из зарегистрированного нами класса (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="a0ca7-240">Then we implement `IPolicyImporterExtension` from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="a0ca7-241">В методе `ImportPolicy()` нужно рассмотреть утверждения в нашем пространстве имен и обработать предназначенные для формирования транспорта и проверки, является ли он многоадресным.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-241">In `ImportPolicy()`, we look through the assertions in our namespace, and process the ones for generating the transport and check whether it is multicast.</span></span> <span data-ttu-id="a0ca7-242">Кроме того, нужно удалить обрабатываемые утверждения из списка утверждений привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-242">We also must remove the assertions we handle from the list of binding assertions.</span></span> <span data-ttu-id="a0ca7-243">И опять при запуске Svcutil.exe существует два варианта интеграции:</span><span class="sxs-lookup"><span data-stu-id="a0ca7-243">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="a0ca7-244">Точка Svcutil.exe к нашему файлу конфигурации с\<помощью /SvcutilConfig: файл>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-244">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="a0ca7-245">добавить раздел конфигурации в файл Svcutil.exe.config, находящийся в том же каталоге, что и файл Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-245">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
<a name="AddingAStandardBinding"></a>
## <a name="adding-a-standard-binding"></a><span data-ttu-id="a0ca7-246">Добавление стандартной привязки</span><span class="sxs-lookup"><span data-stu-id="a0ca7-246">Adding a Standard Binding</span></span>  
 <span data-ttu-id="a0ca7-247">Элемент привязки можно использовать двумя следующими способами.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-247">Our binding element can be used in the following two ways:</span></span>  
  
- <span data-ttu-id="a0ca7-248">С помощью пользовательской привязки: пользовательская привязка позволяет пользователю создать собственную привязку на основе произвольного набора элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-248">Through a custom binding: A custom binding allows the user to create their own binding based on an arbitrary set of binding elements.</span></span>  
  
- <span data-ttu-id="a0ca7-249">С помощью предусмотренной в составе системы привязки, включающей наш элемент привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-249">By using a system-provided binding that includes our binding element.</span></span> <span data-ttu-id="a0ca7-250">WCF предоставляет ряд этих системоопределенных привязок, таких как `BasicHttpBinding`, `NetTcpBinding`и `WsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-250">WCF provides a number of these system-defined bindings, such as `BasicHttpBinding`, `NetTcpBinding`, and `WsHttpBinding`.</span></span> <span data-ttu-id="a0ca7-251">Каждая из них связана с четко определенным профилем.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-251">Each of these bindings is associated with a well-defined profile.</span></span>  
  
 <span data-ttu-id="a0ca7-252">В этом образце реализуется профиль привязки в `SampleProfileUdpBinding`, производном от <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-252">The sample implements profile binding in `SampleProfileUdpBinding`, which derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="a0ca7-253">Привязка `SampleProfileUdpBinding` содержит до четырех элементов привязки: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` и `ReliableSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-253">The `SampleProfileUdpBinding` contains up to four binding elements within it: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement`, and `ReliableSessionBindingElement`.</span></span>  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="a0ca7-254">Добавление пользовательского импортера стандартной привязки</span><span class="sxs-lookup"><span data-stu-id="a0ca7-254">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="a0ca7-255">Svcutil.exe и тип `WsdlImporter` по умолчанию распознают и импортируют определенные системой привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-255">Svcutil.exe and the `WsdlImporter` type, by default, recognizes and imports system-defined bindings.</span></span> <span data-ttu-id="a0ca7-256">В противном случае привязка импортируется как экземпляр `CustomBinding`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-256">Otherwise, the binding gets imported as a `CustomBinding` instance.</span></span> <span data-ttu-id="a0ca7-257">Чтобы Svcutil.exe и тип `WsdlImporter` могли импортировать привязку `SampleProfileUdpBinding`, тип `UdpBindingElementImporter` также выступает в качестве пользовательского импортера стандартной привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-257">To enable Svcutil.exe and the `WsdlImporter` to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="a0ca7-258">Пользовательский импортер стандартной привязки реализует метод `ImportEndpoint` в интерфейсе `IWsdlImportExtension`, чтобы проверить импортированный из метаданных экземпляр класса `CustomBinding` и определить, мог ли он быть сформирован определенной стандартной привязкой.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-258">A custom standard binding importer implements the `ImportEndpoint` method on the `IWsdlImportExtension` interface to examine the `CustomBinding` instance imported from metadata to see whether it could have been generated by a specific standard binding.</span></span>  
  
```csharp
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="a0ca7-259">Как правило, реализация пользовательского импортера стандартной привязки предусматривает проверку свойств импортированных элементов привязки на предмет того, что изменены только свойства, которые могли быть заданы стандартной привязкой, а все остальные свойства имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-259">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="a0ca7-260">Простейшая стратегия для реализации импортера стандартной привязки - создать экземпляр стандартной привязки, распространить на экземпляр стандартной привязки свойства из элементов привязки, поддерживаемые стандартной привязкой, и затем сравнить элементы привязки из стандартной привязки с импортированными элементами привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-260">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>  
  
<a name="AddingConfigurationSupport"></a>
## <a name="adding-configuration-support"></a><span data-ttu-id="a0ca7-261">Добавление поддержки конфигурации</span><span class="sxs-lookup"><span data-stu-id="a0ca7-261">Adding Configuration Support</span></span>  
 <span data-ttu-id="a0ca7-262">Для предоставления транспорта через конфигурацию нужно реализовать два раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-262">To expose our transport through configuration, we must implement two configuration sections.</span></span> <span data-ttu-id="a0ca7-263">Первый - элемент `BindingElementExtensionElement` для `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-263">The first is a `BindingElementExtensionElement` for `UdpTransportBindingElement`.</span></span> <span data-ttu-id="a0ca7-264">За счет этого реализации `CustomBinding` могут ссылаться на наш элемент привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-264">This is so that `CustomBinding` implementations can reference our binding element.</span></span> <span data-ttu-id="a0ca7-265">Второй - `Configuration` для `SampleProfileUdpBinding`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-265">The second is a `Configuration` for our `SampleProfileUdpBinding`.</span></span>  
  
### <a name="binding-element-extension-element"></a><span data-ttu-id="a0ca7-266">Элемент привязки элемента Extension</span><span class="sxs-lookup"><span data-stu-id="a0ca7-266">Binding Element Extension Element</span></span>  
 <span data-ttu-id="a0ca7-267">Раздел `UdpTransportElement` представляет `BindingElementExtensionElement` собой систему конфигурации. `UdpTransportBindingElement`</span><span class="sxs-lookup"><span data-stu-id="a0ca7-267">The section `UdpTransportElement` is a `BindingElementExtensionElement` that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="a0ca7-268">С помощью нескольких простых переопределений в примере определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-268">With a few basic overrides, we define our configuration section name, the type of our binding element and how to create our binding element.</span></span> <span data-ttu-id="a0ca7-269">Затем можно зарегистрировать раздел расширения в файле конфигурации, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-269">We can then register our extension section in a configuration file as shown in the following code.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a0ca7-270">На расширение можно ссылаться из пользовательских привязок, чтобы использовать в качестве транспорта протокол UDP.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-270">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="binding-section"></a><span data-ttu-id="a0ca7-271">Раздел привязки</span><span class="sxs-lookup"><span data-stu-id="a0ca7-271">Binding Section</span></span>  
 <span data-ttu-id="a0ca7-272">Раздел `SampleProfileUdpBindingCollectionElement` представляет `StandardBindingCollectionElement` собой систему конфигурации. `SampleProfileUdpBinding`</span><span class="sxs-lookup"><span data-stu-id="a0ca7-272">The section `SampleProfileUdpBindingCollectionElement` is a `StandardBindingCollectionElement` that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="a0ca7-273">Основная часть реализации делегируется классу `SampleProfileUdpBindingConfigurationElement`, наследуемому от класса `StandardBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-273">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from `StandardBindingElement`.</span></span> <span data-ttu-id="a0ca7-274">Обладает `SampleProfileUdpBindingConfigurationElement` свойствами, которые соответствуют свойствам `SampleProfileUdpBinding`на, `ConfigurationElement` и функции для отображения из связывания.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-274">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="a0ca7-275">Наконец, метод `OnApplyConfiguration` в классе `SampleProfileUdpBinding` переопределяется, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-275">Finally, override the `OnApplyConfiguration` method in our `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
    if (binding == null)
        throw new ArgumentNullException("binding");

    if (binding.GetType() != typeof(SampleProfileUdpBinding))
    {
        throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,
            "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",
            typeof(SampleProfileUdpBinding).AssemblyQualifiedName,
            binding.GetType().AssemblyQualifiedName));
    }
    SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;

    udpBinding.OrderedSession = this.OrderedSession;
    udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;
    udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;
    if (this.ClientBaseAddress != null)
        udpBinding.ClientBaseAddress = ClientBaseAddress;
}
```  
  
 <span data-ttu-id="a0ca7-276">Для регистрации этого обработчика в системе конфигурации в соответствующий файл конфигурации добавляется следующий раздел.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-276">To register this handler with the configuration system, we add the following section to the relevant configuration file.</span></span>  
  
```xml
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
        <sectionGroup name="bindings">  
          <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
        </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="a0ca7-277">После этого на него можно сослаться из раздела конфигурации serviceModel.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-277">It can then be referenced from the serviceModel configuration section.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="the-udp-test-service-and-client"></a><span data-ttu-id="a0ca7-278">Тестовые служба и клиент UDP</span><span class="sxs-lookup"><span data-stu-id="a0ca7-278">The UDP Test Service and Client</span></span>  
 <span data-ttu-id="a0ca7-279">Тестовый код для использования этого примера транспорта находится в каталогах UdpTestService и UdpTestClient.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-279">Test code for using this sample transport is available in the UdpTestService and UdpTestClient directories.</span></span> <span data-ttu-id="a0ca7-280">Код службы состоит из двух тестов. Один из них настраивает привязки и конечные точки из кода, а другой - через конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-280">The service code consists of two tests—one test sets up bindings and endpoints from code and the other does it through configuration.</span></span> <span data-ttu-id="a0ca7-281">Оба теста используют две конечных точки.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-281">Both tests use two endpoints.</span></span> <span data-ttu-id="a0ca7-282">Одна конечная `SampleUdpProfileBinding` точка использует с [ \<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) установлен на `true`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-282">One endpoint uses the `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `true`.</span></span> <span data-ttu-id="a0ca7-283">Другая конечная точка использует пользовательскую привязку с классом `UdpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-283">The other endpoint uses a custom binding with `UdpTransportBindingElement`.</span></span> <span data-ttu-id="a0ca7-284">Это эквивалентно `SampleUdpProfileBinding` использованию с [ \<помощью reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) установлен на `false`.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-284">This is equivalent to using `SampleUdpProfileBinding` with [\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) set to `false`.</span></span> <span data-ttu-id="a0ca7-285">Оба теста создают службу, добавляют для каждой привязки конечную точку, открывают службу и ожидают нажатия пользователем клавиши ВВОД перед тем, как закрыть службу.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-285">Both tests create a service, add an endpoint for each binding, open the service and then wait for the user to hit ENTER before closing the service.</span></span>  
  
 <span data-ttu-id="a0ca7-286">При запуске приложения тестирования службы появится результат следующего вида.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-286">When you start the service test application you should see the following output.</span></span>  
  
```console
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 <span data-ttu-id="a0ca7-287">Затем можно выполнить приложение тестирования клиента относительно опубликованных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-287">You can then run the test client application against the published endpoints.</span></span> <span data-ttu-id="a0ca7-288">Приложение тестирования клиента создает клиент для каждой конечной точки и отправляет им по пять сообщений.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-288">The client test application creates a client for each endpoint and sends five messages to each endpoint.</span></span> <span data-ttu-id="a0ca7-289">Клиент получает следующий результат.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-289">The following output is on the client.</span></span>  
  
```console
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 <span data-ttu-id="a0ca7-290">Полные результаты службы таковы.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-290">The following is the full output on the service.</span></span>  
  
```console
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
   adding 0 + 0  
   adding 1 + 2  
   adding 2 + 4  
   adding 3 + 6  
   adding 4 + 8  
```  
  
 <span data-ttu-id="a0ca7-291">Для выполнения клиентского приложения относительно конечных точек, опубликованных с помощью конфигурации, нажмите в службе клавишу ВВОД и снова запустите тестовый клиент.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-291">To run the client application against endpoints published using configuration, hit ENTER on the service and then run the test client again.</span></span> <span data-ttu-id="a0ca7-292">Служба должна предоставить следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-292">You should see the following output on the service.</span></span>  
  
```console
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 <span data-ttu-id="a0ca7-293">Повторное выполнение клиента дает такие же результаты.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-293">Running the client again yields the same as the preceding results.</span></span>  
  
 <span data-ttu-id="a0ca7-294">Для восстановления кода клиента и конфигурации с помощью Svcutil.exe запустите приложение службы и выполните следующий файл Svcutil.exe из корневого каталога образца.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-294">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe from the root directory of the sample.</span></span>  
  
```console
svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 <span data-ttu-id="a0ca7-295">Обратите внимание, что Svcutil.exe не создает конфигурацию расширения привязки для `SampleProfileUdpBinding`, поэтому ее нужно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-295">Note that Svcutil.exe does not generate the binding extension configuration for the `SampleProfileUdpBinding`, so you must add it manually.</span></span>  
  
```xml
<configuration>  
  <system.serviceModel>
    <extensions>  
      <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
      <bindingExtensions>  
        <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
      </bindingExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a0ca7-296">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="a0ca7-296">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a0ca7-297">Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-297">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="a0ca7-298">Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="a0ca7-298">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a0ca7-299">См. раздел "Тестовые служба и клиент UDP" выше.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-299">Refer to the preceding "The UDP Test Service and Client" section.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a0ca7-300">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-300">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a0ca7-301">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a0ca7-301">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a0ca7-302">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-302">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a0ca7-303">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="a0ca7-303">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`
