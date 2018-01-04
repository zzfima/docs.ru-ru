---
title: HttpCookieSession
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c06efd7450afe93eaecca1e678eb6f8bf5de7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="httpcookiesession"></a><span data-ttu-id="8e9af-102">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="8e9af-102">HttpCookieSession</span></span>
<span data-ttu-id="8e9af-103">В этом образце показано, как построить пользовательский канал протокола, который использует для управления сеансами протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e9af-103">This sample demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span> <span data-ttu-id="8e9af-104">Этот канал обеспечивает взаимодействие между службами [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и клиентами ASMX или между клиентами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и службами ASMX.</span><span class="sxs-lookup"><span data-stu-id="8e9af-104">This channel enables communication between [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services and ASMX clients or between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients and ASMX services.</span></span>  
  
 <span data-ttu-id="8e9af-105">Когда клиент вызывает веб-метод в основанной на сеансах веб-службе ASMX, система [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] выполняет следующие операции:</span><span class="sxs-lookup"><span data-stu-id="8e9af-105">When a client calls a Web method in an ASMX Web service that is session-based, the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] engine does the following:</span></span>  
  
-   <span data-ttu-id="8e9af-106">создает уникальный идентификатор сеанса;</span><span class="sxs-lookup"><span data-stu-id="8e9af-106">Generates a unique ID (session ID).</span></span>  
  
-   <span data-ttu-id="8e9af-107">создает объект сеанса и связывает его с уникальным идентификатором;</span><span class="sxs-lookup"><span data-stu-id="8e9af-107">Generates the session object and associates it with the unique ID.</span></span>  
  
-   <span data-ttu-id="8e9af-108">добавляет уникальный идентификатор в заголовок HTTP-ответа Set-Cookie и отправляет его клиенту;</span><span class="sxs-lookup"><span data-stu-id="8e9af-108">Adds the unique ID to a Set-Cookie HTTP response header and sends it to the client.</span></span>  
  
-   <span data-ttu-id="8e9af-109">определяет клиент в последующих вызовах по идентификатору сеанса и использует его для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="8e9af-109">Identifies the client on subsequent calls based on the session ID it sends to it.</span></span>  
  
 <span data-ttu-id="8e9af-110">Клиент включает этот идентификатор сеанса во все дальнейшие запросы к серверу.</span><span class="sxs-lookup"><span data-stu-id="8e9af-110">The client includes this session ID in its subsequent requests to the server.</span></span> <span data-ttu-id="8e9af-111">Сервер использует идентификатор сеанса клиента, чтобы загружать соответствующий объект сеанса для текущего контекста HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e9af-111">The server uses the session ID from the client to load the appropriate session object for the current HTTP context.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e9af-112">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8e9af-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8e9af-113">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8e9af-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8e9af-114">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e9af-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8e9af-115">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8e9af-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a><span data-ttu-id="8e9af-116">Шаблон обмена сообщениями канала HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="8e9af-116">HttpCookieSession Channel Message Exchange Pattern</span></span>  
 <span data-ttu-id="8e9af-117">В этом примере включаются сеансы для сценариев, подобных применению служб ASMX.</span><span class="sxs-lookup"><span data-stu-id="8e9af-117">This sample enables sessions for ASMX-like scenarios.</span></span> <span data-ttu-id="8e9af-118">В нижней части стека каналов имеется транспорт HTTP, который поддерживает <xref:System.ServiceModel.Channels.IRequestChannel> и <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="8e9af-118">At the bottom of our channel stack, we have the HTTP transport that supports <xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span> <span data-ttu-id="8e9af-119">Именно канал отвечает за то, чтобы предоставлять сеансы каналам стека более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="8e9af-119">It is the job of the channel to provide sessions to the higher levels of the channel stack.</span></span> <span data-ttu-id="8e9af-120">В образце реализуются два канала (<xref:System.ServiceModel.Channels.IRequestSessionChannel> и <xref:System.ServiceModel.Channels.IReplySessionChannel>), поддерживающих сеансы.</span><span class="sxs-lookup"><span data-stu-id="8e9af-120">The sample implements two channels, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> and <xref:System.ServiceModel.Channels.IReplySessionChannel>) that support sessions.</span></span>  
  
## <a name="service-channel"></a><span data-ttu-id="8e9af-121">Канал службы</span><span class="sxs-lookup"><span data-stu-id="8e9af-121">Service Channel</span></span>  
 <span data-ttu-id="8e9af-122">В этом образце создается канал службы в классе `HttpCookieReplySessionChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="8e9af-122">The sample provides a service channel in the `HttpCookieReplySessionChannelListener` class.</span></span> <span data-ttu-id="8e9af-123">Этот класс реализует интерфейс <xref:System.ServiceModel.Channels.IChannelListener> и преобразует канал <xref:System.ServiceModel.Channels.IReplyChannel> из нижнего канала в стеке в канал <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span><span class="sxs-lookup"><span data-stu-id="8e9af-123">This class implements the <xref:System.ServiceModel.Channels.IChannelListener> interface and converts the <xref:System.ServiceModel.Channels.IReplyChannel> channel from lower in the channel stack to a <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="8e9af-124">Этот процесс можно разбить на следующие части.</span><span class="sxs-lookup"><span data-stu-id="8e9af-124">This process can be divided into the following parts:</span></span>  
  
-   <span data-ttu-id="8e9af-125">Когда открывается прослушиватель канала, он принимает от своего внутреннего прослушивателя внутренний канал.</span><span class="sxs-lookup"><span data-stu-id="8e9af-125">When the channel listener is opened, it accepts an inner channel from its inner listener.</span></span> <span data-ttu-id="8e9af-126">Поскольку внутренний прослушиватель является прослушивателем датаграмм, а время существования принятого канала вычитается из времени существования прослушивателя, можно закрыть внутренний прослушиватель и работать только с внутренним каналом.</span><span class="sxs-lookup"><span data-stu-id="8e9af-126">Because the inner listener is a datagram listener and the lifetime of an accepted channel is decoupled from the lifetime of the listener, we can close the inner listener and only hold on to the inner channel</span></span>  
  
    ```  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
-   <span data-ttu-id="8e9af-127">После завершения процесса открытия мы настраиваем цикл сообщений, чтобы получать сообщения от внутреннего канала.</span><span class="sxs-lookup"><span data-stu-id="8e9af-127">When the open process completes, we set up a message loop to receive messages from the inner channel.</span></span>  
  
    ```  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       if (this.completeReceiveCallback == null)  
       {  
          this.completeReceiveCallback = new WaitCallback(CompleteReceiveCallback);  
       }  
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
-   <span data-ttu-id="8e9af-128">Когда сообщение прибывает, канал службы проверяет идентификатор сеанса и демультиплексирует его в соответствующий канал сеанса.</span><span class="sxs-lookup"><span data-stu-id="8e9af-128">When a message arrives, the service channel examines the session identifier and de-multiplexes to the appropriate session channel.</span></span> <span data-ttu-id="8e9af-129">Прослушиватель канала поддерживает словарь, который сопоставляет идентификаторы сеансов с экземплярами каналов сеансов.</span><span class="sxs-lookup"><span data-stu-id="8e9af-129">The channel listener maintains a dictionary that maps the session identifiers to the session channel instances.</span></span>  
  
    ```  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 <span data-ttu-id="8e9af-130">`HttpCookieReplySessionChannel` Класс реализует <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span><span class="sxs-lookup"><span data-stu-id="8e9af-130">The `HttpCookieReplySessionChannel` class implements <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="8e9af-131">Более высокие уровня стека каналов вызывают метод <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> для чтения запросов для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="8e9af-131">Higher levels of the channel stack call the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method to read requests for this session.</span></span> <span data-ttu-id="8e9af-132">У каждого канала сеанса имеется закрытая очередь сообщений, заполняемая каналом службы.</span><span class="sxs-lookup"><span data-stu-id="8e9af-132">Each session channel has a private message queue that is populated by the service channel.</span></span>  
  
```  
InputQueue<RequestContext> requestQueue;  
```  
  
 <span data-ttu-id="8e9af-133">Если происходит вызов метода <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>, а в очереди сообщений нет сообщений, то канал ждет в течение заданного времени, а затем отключается.</span><span class="sxs-lookup"><span data-stu-id="8e9af-133">In the case when someone calls the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method and there are no messages in the message queue, the channel waits for a specified amount of time before shutting itself down.</span></span> <span data-ttu-id="8e9af-134">Это позволяет избавиться от каналов сеансов, созданных для клиентов, не относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e9af-134">This cleans up the session channels created for non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients.</span></span>  
  
 <span data-ttu-id="8e9af-135">Мы используем `channelMapping` для отслеживания `ReplySessionChannels` и не закрываем соответствующий канал `innerChannel`, пока не будут закрыты все принятые каналы.</span><span class="sxs-lookup"><span data-stu-id="8e9af-135">We use the `channelMapping` to track the `ReplySessionChannels`, and we do not close our underlying `innerChannel` until all the accepted channels have been closed.</span></span> <span data-ttu-id="8e9af-136">Таким образом, канал `HttpCookieReplySessionChannel` может существовать после истечения времени существования `HttpCookieReplySessionChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="8e9af-136">This way `HttpCookieReplySessionChannel` can exist beyond the lifetime of `HttpCookieReplySessionChannelListener`.</span></span> <span data-ttu-id="8e9af-137">Кроме того, нам не нужно беспокоиться о попадании прослушивателя под сборку мусора, поскольку принятые каналы сохраняют ссылку на свой прослушиватель с помощью обратного вызова `OnClosed`.</span><span class="sxs-lookup"><span data-stu-id="8e9af-137">We also do not have to worry about the listener getting garbage collected underneath us because the accepted channels keep a reference to their listener through the `OnClosed` callback.</span></span>  
  
## <a name="client-channel"></a><span data-ttu-id="8e9af-138">Клиентский канал</span><span class="sxs-lookup"><span data-stu-id="8e9af-138">Client channel</span></span>  
 <span data-ttu-id="8e9af-139">Соответствующий клиентский канал создается в классе `HttpCookieSessionChannelFactory`.</span><span class="sxs-lookup"><span data-stu-id="8e9af-139">The corresponding client channel is in the `HttpCookieSessionChannelFactory` class.</span></span> <span data-ttu-id="8e9af-140">Во время создания канал фабрика каналов с помощью `HttpCookieRequestSessionChannel` создает оболочку для внутреннего канала запросов.</span><span class="sxs-lookup"><span data-stu-id="8e9af-140">During channel creation, the channel factory wraps the inner request channel with an `HttpCookieRequestSessionChannel`.</span></span> <span data-ttu-id="8e9af-141">Класс `HttpCookieRequestSessionChannel` перенаправляет вызовы в соответствующий канал запросов.</span><span class="sxs-lookup"><span data-stu-id="8e9af-141">The `HttpCookieRequestSessionChannel` class forwards the calls to the underlying request channel.</span></span> <span data-ttu-id="8e9af-142">Когда клиент закрывает прокси, `HttpCookieRequestSessionChannel` отправляет службе сообщение о том, что канал закрывается.</span><span class="sxs-lookup"><span data-stu-id="8e9af-142">When the client closes the proxy, `HttpCookieRequestSessionChannel` sends a message to the service that indicates that the channel is being closed.</span></span> <span data-ttu-id="8e9af-143">Таким образом, стек каналов службы может безопасно закрыть используемый канал сеанса.</span><span class="sxs-lookup"><span data-stu-id="8e9af-143">Thus, the service channel stack can gracefully shutdown the session channel that is in use.</span></span>  
  
## <a name="binding-and-binding-element"></a><span data-ttu-id="8e9af-144">Привязка и элемент привязки</span><span class="sxs-lookup"><span data-stu-id="8e9af-144">Binding and Binding Element</span></span>  
 <span data-ttu-id="8e9af-145">Следующим шагом после создания каналов клиента и службы является их интеграция в среду выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e9af-145">After creating the service and client channels, the next step is to integrate them into the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime.</span></span> <span data-ttu-id="8e9af-146">Каналы предоставляются среде [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] через привязки и элементы привязки.</span><span class="sxs-lookup"><span data-stu-id="8e9af-146">Channels are exposed to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] through bindings and binding elements.</span></span> <span data-ttu-id="8e9af-147">Привязка состоит из одного или нескольких элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="8e9af-147">A binding consists of one or many binding elements.</span></span> <span data-ttu-id="8e9af-148">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] имеется несколько привязок, определенных системой, например BasicHttpBinding или WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="8e9af-148">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] offers several system-defined bindings; for example, BasicHttpBinding or WSHttpBinding.</span></span> <span data-ttu-id="8e9af-149">Класс `HttpCookieSessionBindingElement` содержит реализацию элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="8e9af-149">The `HttpCookieSessionBindingElement` class contains the implementation for the binding element.</span></span> <span data-ttu-id="8e9af-150">Он переопределяет прослушиватель канала и методы создания фабрики канала для создания нужных экземпляров прослушивателя канала и фабрики каналов.</span><span class="sxs-lookup"><span data-stu-id="8e9af-150">It overrides the channel listener and channel factory creation methods to do the necessary channel listener or channel factory instantiations.</span></span>  
  
 <span data-ttu-id="8e9af-151">В этом образце для описания службы используются утверждения политики.</span><span class="sxs-lookup"><span data-stu-id="8e9af-151">The sample uses policy assertions for the service description.</span></span> <span data-ttu-id="8e9af-152">Это позволяет образцу публиковать свои требования к каналам для других клиентов, которые могут пользоваться службой.</span><span class="sxs-lookup"><span data-stu-id="8e9af-152">This allows the sample to publish its channel requirements to other clients that can consume the service.</span></span> <span data-ttu-id="8e9af-153">Например, этот элемент привязки публикует утверждения политики, позволяющие потенциальным клиентам узнать, служба поддерживает сеансы.</span><span class="sxs-lookup"><span data-stu-id="8e9af-153">For example, this binding element publishes policy assertions to let potential clients know that it supports sessions.</span></span> <span data-ttu-id="8e9af-154">Поскольку в конфигурации элемента привязки этого образца включено свойство `ExchangeTerminateMessage`, оно добавляет необходимые утверждения, чтобы показать, что служба поддерживает дополнительные действия обмена сообщениями для завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="8e9af-154">Because the sample enables the `ExchangeTerminateMessage` property in the binding element configuration, it adds the necessary assertions to show that the service supports an extra message exchange action to terminate the session conversation.</span></span> <span data-ttu-id="8e9af-155">Клиенты могут использовать это действие.</span><span class="sxs-lookup"><span data-stu-id="8e9af-155">Clients can then use this action.</span></span> <span data-ttu-id="8e9af-156">В следующем коде WSDL показаны утверждения политики, созданные на базе элемента `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="8e9af-156">The following WSDL code shows the policy assertions created from the `HttpCookieSessionBindingElement`.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="8e9af-157">Класс `HttpCookieSessionBinding` является предоставляемой системой привязкой, которая использует описанный выше элемент привязки.</span><span class="sxs-lookup"><span data-stu-id="8e9af-157">The `HttpCookieSessionBinding` class is a system-provided binding that uses the binding element described previously.</span></span>  
  
## <a name="adding-the-channel-to-the-configuration-system"></a><span data-ttu-id="8e9af-158">Добавление канала в систему конфигурации</span><span class="sxs-lookup"><span data-stu-id="8e9af-158">Adding the Channel to the Configuration System</span></span>  
 <span data-ttu-id="8e9af-159">В этом образце имеется два канала, делающие канал доступным через конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8e9af-159">The sample provides two classes that expose the sample channel through configuration.</span></span> <span data-ttu-id="8e9af-160">Первый - элемент <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> для `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="8e9af-160">The first is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> for the `HttpCookieSessionBindingElement`.</span></span> <span data-ttu-id="8e9af-161">Основная часть реализации делегируется классу `HttpCookieSessionBindingConfigurationElement`, наследуемому от класса <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="8e9af-161">The bulk of the implementation is delegated to the `HttpCookieSessionBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="8e9af-162">Элемент `HttpCookieSessionBindingConfigurationElement` имеет свойства, которые соответствуют свойствам элемента `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="8e9af-162">The `HttpCookieSessionBindingConfigurationElement` has properties that correspond to the properties on `HttpCookieSessionBindingElement`.</span></span>  
  
### <a name="binding-element-extension-section"></a><span data-ttu-id="8e9af-163">Раздел расширения элемента привязки</span><span class="sxs-lookup"><span data-stu-id="8e9af-163">Binding Element Extension Section</span></span>  
 <span data-ttu-id="8e9af-164">Раздел `HttpCookieSessionBindingElementSection` — <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> , предоставляющий `HttpCookieSessionBindingElement` системе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8e9af-164">The section `HttpCookieSessionBindingElementSection` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `HttpCookieSessionBindingElement` to the configuration system.</span></span> <span data-ttu-id="8e9af-165">С помощью нескольких простых переопределений определяется имя раздела конфигурации, тип элемента привязки и способ создания элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="8e9af-165">With a few overrides the configuration section name, the type of the binding element and how to create the binding element are defined.</span></span> <span data-ttu-id="8e9af-166">Мы можем затем зарегистрировать раздел расширения в файле конфигурации следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8e9af-166">We can then register the extension section in a configuration file as follows:</span></span>  
  
```xml  
<configuration>        
    <system.serviceModel>        
      <extensions>          
        <bindingElementExtensions>            
          <add name="httpCookieSession"   
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,   
                    HttpCookieSessionExtension, Version=1.0.0.0,   
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>        
    </system.serviceModel>    
</configuration>  
```  
  
## <a name="test-code"></a><span data-ttu-id="8e9af-167">Тестовый код</span><span class="sxs-lookup"><span data-stu-id="8e9af-167">Test Code</span></span>  
 <span data-ttu-id="8e9af-168">Тестовый код для использования этого примера транспорта находится в каталогах Client и Service.</span><span class="sxs-lookup"><span data-stu-id="8e9af-168">Test code for using this sample transport is available in the Client and Service directories.</span></span> <span data-ttu-id="8e9af-169">Он состоит из двух тестов-один тест использует привязку с `allowCookies` значение `true` на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="8e9af-169">It consists of two tests—one test uses a binding with `allowCookies` set to `true` on the client.</span></span> <span data-ttu-id="8e9af-170">Второй тест включает на привязке явное отключение (с помощью обмена сообщениями завершения).</span><span class="sxs-lookup"><span data-stu-id="8e9af-170">The second test enables explicit shutdown (using the terminate message exchange) on the binding.</span></span>  
  
 <span data-ttu-id="8e9af-171">При запуске примера результат должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8e9af-171">When you run the sample, you should see the following output:</span></span>  
  
```  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8e9af-172">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="8e9af-172">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8e9af-173">Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8e9af-173">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="8e9af-174">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8e9af-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="8e9af-175">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8e9af-175">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="8e9af-176">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8e9af-176">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9af-177">См. также</span><span class="sxs-lookup"><span data-stu-id="8e9af-177">See Also</span></span>
