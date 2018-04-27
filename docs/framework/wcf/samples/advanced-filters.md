---
title: Дополнительные фильтры
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a374765317751a5adc241941a0c0dc613a3ea2cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="advanced-filters"></a><span data-ttu-id="84fc5-102">Дополнительные фильтры</span><span class="sxs-lookup"><span data-stu-id="84fc5-102">Advanced Filters</span></span>
<span data-ttu-id="84fc5-103">В этом образце демонстрируется служба маршрутизации [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84fc5-103">This sample demonstrates a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] routing service.</span></span> <span data-ttu-id="84fc5-104">Служба маршрутизации - это компонент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который упрощает включение маршрутизатора на основе содержимого в приложение.</span><span class="sxs-lookup"><span data-stu-id="84fc5-104">The routing service is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="84fc5-105">'В этом образце стандартный образец [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator применяется для связи с использованием службы маршрутизации</span><span class="sxs-lookup"><span data-stu-id="84fc5-105">This sample adapts the standard [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Calculator sample to communicate using the routing service.</span></span> <span data-ttu-id="84fc5-106">В этом образце показано определение логики маршрутизации на основе содержимого посредством использования фильтров сообщений и таблиц фильтров сообщений.</span><span class="sxs-lookup"><span data-stu-id="84fc5-106">This sample shows how to define content-based routing logic through the use of message filters and message filter tables.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84fc5-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="84fc5-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="84fc5-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="84fc5-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="84fc5-109">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="84fc5-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="84fc5-110">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="84fc5-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## <a name="sample-details"></a><span data-ttu-id="84fc5-111">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="84fc5-111">Sample Details</span></span>  
 <span data-ttu-id="84fc5-112">В следующей таблице представлены фильтры сообщений, которые добавляются в таблицу фильтров сообщений службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="84fc5-112">The following table shows the message filters that are added to the message filter table of the routing service.</span></span>  
  
|<span data-ttu-id="84fc5-113">Фильтр</span><span class="sxs-lookup"><span data-stu-id="84fc5-113">Filter</span></span>|<span data-ttu-id="84fc5-114">Правило</span><span class="sxs-lookup"><span data-stu-id="84fc5-114">Rule</span></span>|<span data-ttu-id="84fc5-115">Приоритет</span><span class="sxs-lookup"><span data-stu-id="84fc5-115">Priority</span></span>|  
|------------|----------|--------------|  
|<span data-ttu-id="84fc5-116">Если (имеет заголовок)</span><span class="sxs-lookup"><span data-stu-id="84fc5-116">If (has header)</span></span>|<span data-ttu-id="84fc5-117">Округление</span><span class="sxs-lookup"><span data-stu-id="84fc5-117">Rounding</span></span>|<span data-ttu-id="84fc5-118">2</span><span class="sxs-lookup"><span data-stu-id="84fc5-118">2</span></span>|  
|<span data-ttu-id="84fc5-119">Если (показан на Ep2)</span><span class="sxs-lookup"><span data-stu-id="84fc5-119">If (showed up on Ep2)</span></span>|<span data-ttu-id="84fc5-120">Регулярное</span><span class="sxs-lookup"><span data-stu-id="84fc5-120">Regular</span></span>|<span data-ttu-id="84fc5-121">1</span><span class="sxs-lookup"><span data-stu-id="84fc5-121">1</span></span>|  
|<span data-ttu-id="84fc5-122">Если (показан с Address2)</span><span class="sxs-lookup"><span data-stu-id="84fc5-122">If (showed up with Address2)</span></span>|<span data-ttu-id="84fc5-123">Округление</span><span class="sxs-lookup"><span data-stu-id="84fc5-123">Rounding</span></span>|<span data-ttu-id="84fc5-124">1</span><span class="sxs-lookup"><span data-stu-id="84fc5-124">1</span></span>|  
|<span data-ttu-id="84fc5-125">Если (RoundRobin1)</span><span class="sxs-lookup"><span data-stu-id="84fc5-125">If (RoundRobin1)</span></span>|<span data-ttu-id="84fc5-126">Регулярное</span><span class="sxs-lookup"><span data-stu-id="84fc5-126">Regular</span></span>|<span data-ttu-id="84fc5-127">0</span><span class="sxs-lookup"><span data-stu-id="84fc5-127">0</span></span>|  
|<span data-ttu-id="84fc5-128">Если (RoundRobin2)</span><span class="sxs-lookup"><span data-stu-id="84fc5-128">If (RoundRobin2)</span></span>|<span data-ttu-id="84fc5-129">Округление</span><span class="sxs-lookup"><span data-stu-id="84fc5-129">Rounding</span></span>|<span data-ttu-id="84fc5-130">0</span><span class="sxs-lookup"><span data-stu-id="84fc5-130">0</span></span>|  
  
 <span data-ttu-id="84fc5-131">Фильтры сообщений и таблицы фильтров сообщений можно создавать и настраивать с помощью кода или в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="84fc5-131">The message filters and message filter tables can be created and configured either through code or in the application configuration file.</span></span> <span data-ttu-id="84fc5-132">Для этого образца есть фильтры сообщений и таблицы фильтров сообщений, определенные с помощью кода в файле RoutingService\routing.cs, а также определенные в файле конфигурации приложения RoutingService\App.config.</span><span class="sxs-lookup"><span data-stu-id="84fc5-132">For this sample, you can find the message filters and message filter tables defined through code in the RoutingService\routing.cs file, or defined in the application configuration file in the RoutingService\App.config file.</span></span> <span data-ttu-id="84fc5-133">В следующих абзацах описывается создание фильтров сообщений и таблиц фильтров сообщений для этого образца с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="84fc5-133">The following paragraphs describe how the message filters and message filter tables are created for this sample through code.</span></span>  
  
 <span data-ttu-id="84fc5-134">Сначала фильтр <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> ищет пользовательский заголовок.</span><span class="sxs-lookup"><span data-stu-id="84fc5-134">First, an <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> looks for the custom header.</span></span> <span data-ttu-id="84fc5-135">Следует отметить, что результатом <xref:System.ServiceModel.WSHttpBinding> является версия конверта с использованием SOAP 1.2, поэтому инструкция XPath настроена для использования пространства имен SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="84fc5-135">Note that <xref:System.ServiceModel.WSHttpBinding> results in an envelope version using SOAP 1.2, so the XPath statement is defined to use the SOAP 1.2 namespace.</span></span> <span data-ttu-id="84fc5-136">Диспетчер пространств имен по умолчанию для <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> определяет пригодный для использования префикс для пространства имен SOAP 1.2, /s12.</span><span class="sxs-lookup"><span data-stu-id="84fc5-136">The default namespace manager for <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>s already defines a prefix for the SOAP 1.2 namespace, /s12, which can be used.</span></span> <span data-ttu-id="84fc5-137">Однако диспетчер пространств имен по умолчанию не имеет пользовательского пространства имен, с помощью которого клиент определяет фактическое значение заголовка, поэтому необходимо задать префикс.</span><span class="sxs-lookup"><span data-stu-id="84fc5-137">However, the default namespace manager does not have the custom namespace that the client uses to define the actual header value, so that prefix must be defined.</span></span> <span data-ttu-id="84fc5-138">Любое сообщение с этим заголовком будет соответствовать фильтру.</span><span class="sxs-lookup"><span data-stu-id="84fc5-138">Any message that shows up with this header matches this filter.</span></span>  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
```  
  
 <span data-ttu-id="84fc5-139">Вторым фильтром является <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, ему соответствует любое сообщение, полученное в конечной точке `calculatorEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="84fc5-139">The second filter is an <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, which matches any message that was received on the `calculatorEndpoint`.</span></span> <span data-ttu-id="84fc5-140">Имя конечной точки определяется при создании объекта конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="84fc5-140">The endpoint name is defined when a service endpoint object is created.</span></span>  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
```  
  
 <span data-ttu-id="84fc5-141">Третьим фильтром является <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="84fc5-141">The third filter is a <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>.</span></span> <span data-ttu-id="84fc5-142">Этому фильтру соответствует любое сообщение, поступающее в конечную точку, адрес которой соответствует указанному префиксу адреса (или передней части).</span><span class="sxs-lookup"><span data-stu-id="84fc5-142">This matches any message that showed up on an endpoint with an address that matches the address prefix (or the front portion) provided.</span></span> <span data-ttu-id="84fc5-143">В этом примере определяется префикс адреса «http://localhost/routingservice/router/rounding/».</span><span class="sxs-lookup"><span data-stu-id="84fc5-143">In this example the address prefix is defined as "http://localhost/routingservice/router/rounding/".</span></span> <span data-ttu-id="84fc5-144">Это означает, что любые входящие сообщения, адресованные «http://localhost/routingservice/router/rounding/\*» соответствует этому фильтру.</span><span class="sxs-lookup"><span data-stu-id="84fc5-144">This means that any incoming messages that are addressed to "http://localhost/routingservice/router/rounding/\*" are matched by this filter.</span></span> <span data-ttu-id="84fc5-145">В этом случае это сообщения, которые отображаются на конечную точку Округляющего калькулятора, который имеет адрес «http://localhost/routingservice/router/rounding/calculator».</span><span class="sxs-lookup"><span data-stu-id="84fc5-145">In this case, it is messages that show up on the Rounding Calculator endpoint, which has the address of "http://localhost/routingservice/router/rounding/calculator".</span></span>  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
```  
  
 <span data-ttu-id="84fc5-146">Последние два фильтра сообщений являются пользовательскими <xref:System.ServiceModel.Dispatcher.MessageFilter>.</span><span class="sxs-lookup"><span data-stu-id="84fc5-146">The last two message filters are custom <xref:System.ServiceModel.Dispatcher.MessageFilter>s.</span></span> <span data-ttu-id="84fc5-147">В этом примере используется фильтр сообщений RoundRobin.</span><span class="sxs-lookup"><span data-stu-id="84fc5-147">In this example, a "RoundRobin" message filter is used.</span></span> <span data-ttu-id="84fc5-148">Этот фильтр сообщений создан в предоставленном файле RoutingService\RoundRobinMessageFilter.cs.</span><span class="sxs-lookup"><span data-stu-id="84fc5-148">This message filter is created in the provided RoutingService\RoundRobinMessageFilter.cs file.</span></span> <span data-ttu-id="84fc5-149">Собранные в одну группу, эти фильтры попеременно извещают о своем соответствии и несоответствии сообщению, при этом каждый раз только один из них возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="84fc5-149">These filters, when set to the same group, alternate between reporting that they match the message and that they do not, such that only one of them responds `true` at a time.</span></span>  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
```  
  
 <span data-ttu-id="84fc5-150">Затем все эти сообщения добавляются в таблицу <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>.</span><span class="sxs-lookup"><span data-stu-id="84fc5-150">Next, all of those messages are added to a <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>.</span></span> <span data-ttu-id="84fc5-151">При этом указываются приоритеты, в соответствии с которыми формируется порядок выполнения фильтров таблицей фильтров сообщений.</span><span class="sxs-lookup"><span data-stu-id="84fc5-151">In doing so, priorities are specified to influence the order in which the message filter table executes the filters.</span></span> <span data-ttu-id="84fc5-152">Чем выше приоритет, тем скорее фильтр будет выполнен, чем ниже приоритет, тем позднее будет выполнен фильтр.</span><span class="sxs-lookup"><span data-stu-id="84fc5-152">The higher the priority, the sooner the filter is executed; the lower the priority, the later a filter is executed.</span></span> <span data-ttu-id="84fc5-153">Так, фильтр с приоритетом 2 выполняется перед выполнением фильтра с приоритетом 1.</span><span class="sxs-lookup"><span data-stu-id="84fc5-153">Thus a filter at priority 2 runs before a filter at priority 1.</span></span> <span data-ttu-id="84fc5-154">Если приоритет не указан, то уровень приоритета по умолчанию - 0.</span><span class="sxs-lookup"><span data-stu-id="84fc5-154">The default priority level if none is specified is 0.</span></span> <span data-ttu-id="84fc5-155">Таблица фильтров сообщений выполняет все фильтры на данном уровне приоритета, после чего переходит на следующий, более низкий уровень приоритета.</span><span class="sxs-lookup"><span data-stu-id="84fc5-155">A message filter table executes all of the filters at a given priority level before moving to the next lowest priority level.</span></span> <span data-ttu-id="84fc5-156">Если на определенном уровне приоритета обнаружено совпадение, то таблица фильтров сообщений не продолжает поиск совпадений на следующем, более низком уровне приоритета.</span><span class="sxs-lookup"><span data-stu-id="84fc5-156">If a match is found at a particular priority, then the message filter table does not continue trying to find matches at the next lower priority.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84fc5-157">Несмотря на то, что в этом примере показано, как использовать приоритеты фильтров сообщений, в целом для обеспечения большей производительности лучше проектировать и настраивать фильтры так, чтобы для правильной работы им не требовалось назначать приоритеты.</span><span class="sxs-lookup"><span data-stu-id="84fc5-157">While this example shows how to use message filter priorities, in general it is more performant and better design to design and configure your filters such that they do not require prioritization to function correctly.</span></span>  
  
 <span data-ttu-id="84fc5-158">Первым добавляемым фильтром является фильтр XPath, ему устанавливается приоритет 2.</span><span class="sxs-lookup"><span data-stu-id="84fc5-158">The first filter to be added is the XPath filter and its priority is set to 2.</span></span> <span data-ttu-id="84fc5-159">Этот фильтр сообщений выполняется первым.</span><span class="sxs-lookup"><span data-stu-id="84fc5-159">This is the first message filter that executes.</span></span> <span data-ttu-id="84fc5-160">Если он обнаруживает пользовательский заголовок, то сообщение направляется в конечную точку округляющего калькулятора независимо от результатов выполнения других фильтров.</span><span class="sxs-lookup"><span data-stu-id="84fc5-160">If it finds the custom header, regardless of what the results of the other filters would be, the message is routed to the Rounding Calculator endpoint.</span></span>  
  
 <span data-ttu-id="84fc5-161">На уровне приоритета 1 добавляются два фильтра.</span><span class="sxs-lookup"><span data-stu-id="84fc5-161">At priority 1, two filters are added.</span></span> <span data-ttu-id="84fc5-162">Опять-таки эти фильтры выполняются, только если сообщение не соответствует фильтру XPath с приоритетом 2.</span><span class="sxs-lookup"><span data-stu-id="84fc5-162">Again, these only run if the XPath filter at priority 2 does not match the message.</span></span> <span data-ttu-id="84fc5-163">Эти два фильтра представляют два разных способа определения того, куда направлялось сообщение, когда оно появилось.</span><span class="sxs-lookup"><span data-stu-id="84fc5-163">These two filters show two different ways to determine where the message was addressed when it showed up.</span></span> <span data-ttu-id="84fc5-164">Поскольку два этих фильтра, по сути, проверяют, пришло ли сообщение в одну из двух конечных точек, они могут выполняться на одном уровне приоритета, так как не могут одновременно возвратить значение `true`.</span><span class="sxs-lookup"><span data-stu-id="84fc5-164">Because the two filters effectively check to see whether the message arrived at one of the two endpoints, they can be run at the same priority level because they do not both return `true` at the same time.</span></span>  
  
 <span data-ttu-id="84fc5-165">Наконец, на уровне приоритета 0 (самый низкий приоритет) выполняются фильтры сообщений RoundRobin.</span><span class="sxs-lookup"><span data-stu-id="84fc5-165">Finally, at Priority 0 (the lowest priority) run the RoundRobin message filters.</span></span> <span data-ttu-id="84fc5-166">Поскольку фильтрам задается одинаковое имя группы, сообщение может одновременно соответствовать только одному из них.</span><span class="sxs-lookup"><span data-stu-id="84fc5-166">Because the filters are configured with the same group name, only one of them matches at a time.</span></span> <span data-ttu-id="84fc5-167">Поскольку все сообщения с пользовательским заголовком, а также все сообщения, адресованные определенным виртуализованным конечным точкам, перенаправлены, то фильтрами RoundRobin обрабатываются только те сообщения, которые были адресованы конечной точке маршрутизатора по умолчанию и которые не содержат пользовательского заголовка.</span><span class="sxs-lookup"><span data-stu-id="84fc5-167">Because all messages with the custom header have been routed and all those addressed to the specific virtualized endpoints, messages handled by the RoundRobin message filters are only messages that were addressed to the default router endpoint without the custom header.</span></span> <span data-ttu-id="84fc5-168">Поскольку эти сообщения переключают сообщение для каждого вызова, половина операций переходит в конечную точку обычного калькулятора, а вторая половина - в конечную точку округляющего калькулятора.</span><span class="sxs-lookup"><span data-stu-id="84fc5-168">Because these messages switch on a message for each call, half of the operations go to the Regular Calculator endpoint and the other half go to the Rounding Calculator endpoint.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="84fc5-169">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="84fc5-169">To use this sample</span></span>  
  
1.  <span data-ttu-id="84fc5-170">Откройте файл AdvancedFilters.sln с помощью [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84fc5-170">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open AdvancedFilters.sln.</span></span>  
  
2.  <span data-ttu-id="84fc5-171">Чтобы открыть **обозревателе решений**выберите **обозревателе решений** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="84fc5-171">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="84fc5-172">В Visual Studio, нажмите клавишу F5 или CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="84fc5-172">Press F5 or CTRL+SHIFT+B in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="84fc5-173">Если вы хотите автоматически загружались все необходимые проекты при нажатии клавиши F5, щелкните правой кнопкой мыши решение и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="84fc5-173">If you would like to auto-launch the necessary projects when you press F5, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="84fc5-174">Выберите **запускаемый проект** узле **общие свойства** в левой области.</span><span class="sxs-lookup"><span data-stu-id="84fc5-174">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="84fc5-175">Выберите **несколько запускаемых проектов** переключатель и задать все проекты, которые нужно иметь **запустить** действие.</span><span class="sxs-lookup"><span data-stu-id="84fc5-175">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="84fc5-176">Если проект строится с помощью клавиш CTRL+SHIFT+B, необходимо запустить следующие приложения.</span><span class="sxs-lookup"><span data-stu-id="84fc5-176">If you build the project with CTRL+SHIFT+B, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="84fc5-177">Клиентская часть калькулятора (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="84fc5-177">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="84fc5-178">Служба -калькулятора (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="84fc5-178">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="84fc5-179">Служба калькулятора с маршрутизацией (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="84fc5-179">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="84fc5-180">RoutingService (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="84fc5-180">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="84fc5-181">В консольном окне клиентской части калькулятора нажмите клавишу ВВОД, чтобы запустить клиент.</span><span class="sxs-lookup"><span data-stu-id="84fc5-181">In the console window of the Calculator client, press ENTER to start the client.</span></span> <span data-ttu-id="84fc5-182">Клиент возвращает список конечных точек назначения для выбора.</span><span class="sxs-lookup"><span data-stu-id="84fc5-182">The client returns a list of destination endpoints to choose from.</span></span>  
  
5.  <span data-ttu-id="84fc5-183">Выберите конечную точку назначения, введя соответствующую ей букву, и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="84fc5-183">Choose a destination endpoint by typing its corresponding letter and press ENTER.</span></span>  
  
6.  <span data-ttu-id="84fc5-184">Затем клиент спросит, требуется ли добавить пользовательский заголовок.</span><span class="sxs-lookup"><span data-stu-id="84fc5-184">Next, the client asks you if you want to add a custom header.</span></span> <span data-ttu-id="84fc5-185">Введите Y, чтобы сказать «Да», N, чтобы сказать «Нет», и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="84fc5-185">Press Y for Yes or N for No, then press ENTER.</span></span>  
  
7.  <span data-ttu-id="84fc5-186">Результат будет зависеть от выбранных вариантов.</span><span class="sxs-lookup"><span data-stu-id="84fc5-186">Depending on the selections you made, you should see different outputs.</span></span>  
  
    1.  <span data-ttu-id="84fc5-187">Далее приведен вывод, возвращаемый при добавлении в сообщение пользовательского заголовка.</span><span class="sxs-lookup"><span data-stu-id="84fc5-187">The following is the output returned if you added a custom header to the messages.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="84fc5-188">Далее приведен вывод, возвращаемый при выборе конечной точки округляющего калькулятора без пользовательского заголовка.</span><span class="sxs-lookup"><span data-stu-id="84fc5-188">The following is the output returned if you chose the Rounding Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    3.  <span data-ttu-id="84fc5-189">Далее приведен вывод, возвращаемый при выборе конечной точки обычного калькулятора без пользовательского заголовка.</span><span class="sxs-lookup"><span data-stu-id="84fc5-189">The following is the output returned if you chose the Regular Calculator endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68. 46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
    4.  <span data-ttu-id="84fc5-190">Далее приведен вывод, возвращаемый при выборе конечной точки маршрутизатора по умолчанию без пользовательского заголовка.</span><span class="sxs-lookup"><span data-stu-id="84fc5-190">The following is the output returned if you chose the Default Router endpoint without a custom header.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.14285714285714  
        ```  
  
8.  <span data-ttu-id="84fc5-191">Служба калькулятора и служба округляющего калькулятора также печатают журнал вызванных операций в соответствующих консольных окнах.</span><span class="sxs-lookup"><span data-stu-id="84fc5-191">The Calculator Service and the Rounding Calculator Service also prints out a log of the operations invoked to their respective console windows.</span></span>  
  
9. <span data-ttu-id="84fc5-192">В окне консоли клиента введите `quit` и нажмите клавишу ВВОД для выхода.</span><span class="sxs-lookup"><span data-stu-id="84fc5-192">In the client console window, type `quit` and press ENTER to exit.</span></span>  
  
10. <span data-ttu-id="84fc5-193">Нажмите клавишу ВВОД в окнах консоли служб, чтобы завершить службы.</span><span class="sxs-lookup"><span data-stu-id="84fc5-193">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="84fc5-194">Настраивается в коде или в файле App.config</span><span class="sxs-lookup"><span data-stu-id="84fc5-194">Configurable Via Code or App.config</span></span>  
 <span data-ttu-id="84fc5-195">В поставляемой конфигурации образца поведение маршрутизатора определяется в файле App.config.</span><span class="sxs-lookup"><span data-stu-id="84fc5-195">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="84fc5-196">Кроме того, можно изменить имя файла RoutingService\App.config на другое, чтобы он не был распознан, и удалить метки комментария с вызова метода `ConfigureRouterViaCode()` в файле RoutingService\routing.cs.</span><span class="sxs-lookup"><span data-stu-id="84fc5-196">You can also change the name of the RoutingService\App.config file to something else so that it is not recognized and uncomment the method call to `ConfigureRouterViaCode()` in RoutingService\routing.cs.</span></span> <span data-ttu-id="84fc5-197">Поведение маршрутизатора будет одинаковым для обоих методов.</span><span class="sxs-lookup"><span data-stu-id="84fc5-197">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="84fc5-198">Сценарий</span><span class="sxs-lookup"><span data-stu-id="84fc5-198">Scenario</span></span>  
 <span data-ttu-id="84fc5-199">В этом образце показан маршрутизатор, работающий на основе содержимого и предоставляющий доступ к нескольким типам реализации служб через одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="84fc5-199">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="84fc5-200">Реальный сценарий</span><span class="sxs-lookup"><span data-stu-id="84fc5-200">Real World Scenario</span></span>  
 <span data-ttu-id="84fc5-201">Компания Contoso планирует провести виртуализацию всех служб, чтобы сделать общедоступной только одну конечную точку, через которую возможен доступ к нескольким различным типам служб.</span><span class="sxs-lookup"><span data-stu-id="84fc5-201">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="84fc5-202">В этом случае применяются функции маршрутизации на основе содержимого, чтобы определить назначение для отправки входящих запросов.</span><span class="sxs-lookup"><span data-stu-id="84fc5-202">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84fc5-203">См. также</span><span class="sxs-lookup"><span data-stu-id="84fc5-203">See Also</span></span>  
 [<span data-ttu-id="84fc5-204">Образцы размещения и сохраняемости образцы</span><span class="sxs-lookup"><span data-stu-id="84fc5-204">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
