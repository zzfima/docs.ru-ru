---
title: Динамическая реконфигурация
ms.date: 03/30/2017
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
ms.openlocfilehash: a147a1d6cf61001832661376363ecc850ecad309
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157146"
---
# <a name="dynamic-reconfiguration"></a><span data-ttu-id="77cb6-102">Динамическая реконфигурация</span><span class="sxs-lookup"><span data-stu-id="77cb6-102">Dynamic Reconfiguration</span></span>
<span data-ttu-id="77cb6-103">В этом примере демонстрируется служба маршрутизации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="77cb6-103">This sample demonstrates the Windows Communication Foundation (WCF) routing service.</span></span> <span data-ttu-id="77cb6-104">Служба маршрутизации является компонентом WCF, который упрощает Включение маршрутизатора на основе содержимого в приложении.</span><span class="sxs-lookup"><span data-stu-id="77cb6-104">The routing service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="77cb6-105">В этом образце адаптирует стандартный образец калькулятора WCF для связи с использованием службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="77cb6-105">This sample adapts the standard WCF Calculator Sample to communicate using the routing service.</span></span> <span data-ttu-id="77cb6-106">Этот образец показывает, как можно динамически переконфигурировать службу маршрутизации во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="77cb6-106">This sample shows how the routing service can be dynamically reconfigured during runtime.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="77cb6-107">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="77cb6-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="77cb6-108">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="77cb6-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="77cb6-109">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="77cb6-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="77cb6-110">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="77cb6-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a><span data-ttu-id="77cb6-111">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="77cb6-111">Sample Details</span></span>  
 <span data-ttu-id="77cb6-112">Для того, чтобы динамически переконфигурировать службу маршрутизации во время выполнения, данный образец запускает таймер, который каждые пять секунд создает и применяет новый объект <xref:System.ServiceModel.Routing.RoutingConfiguration>.</span><span class="sxs-lookup"><span data-stu-id="77cb6-112">To dynamically reconfigure the routing service during runtime, this sample fires a timer every five seconds that creates a new <xref:System.ServiceModel.Routing.RoutingConfiguration> object and applies it.</span></span> <span data-ttu-id="77cb6-113">Данная конфигурация ссылается либо на стандартную конечную точку калькулятора, либо на конечную точку округляющего калькулятора.</span><span class="sxs-lookup"><span data-stu-id="77cb6-113">This configuration references either the regular Calculator endpoint or the Rounding Calculator endpoint.</span></span> <span data-ttu-id="77cb6-114">Клиентское приложение калькулятора получает сообщения от одной службы или от другой, в зависимости от того, как настроена в данный момент служба маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="77cb6-114">The Calculator Client application has its messages returned from one service or the other, depending on which one the routing service is configured to route to at that time.</span></span>  
  
 <span data-ttu-id="77cb6-115">При этом используется возможность динамической переконфигурации службы маршрутизации при помощи пользовательского поведения.</span><span class="sxs-lookup"><span data-stu-id="77cb6-115">The routing service’s capabilitiy for dynamic reconfiguration through a custom behavior is used.</span></span> <span data-ttu-id="77cb6-116">Пользовательское поведение присоединяет расширение службы, которое содержит простой потоковой таймер, срабатывающий каждые пять секунд, в результате чего производится обращение к методу обратного вызова `UpdateRules`.</span><span class="sxs-lookup"><span data-stu-id="77cb6-116">This custom behavior attaches a service extension, which contains a simple thread timer that fires every five seconds, which results in a callback to the `UpdateRules` method.</span></span> <span data-ttu-id="77cb6-117">Этот обратный вызов создает и применяет новую конфигурацию маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="77cb6-117">This callback creates and applies the new routing configuration.</span></span> <span data-ttu-id="77cb6-118">В настоящем развертывании этот обратный вызов, скорее всего, будет выполнен в результате другого типа события, например уведомления о событии SQL или объявления об обнаружении WS.</span><span class="sxs-lookup"><span data-stu-id="77cb6-118">In an actual deployment, this callback would likely be accomplished as a result of some other type of event, such as a SQL-Event notification, or a WS-Discovery announcement.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="77cb6-119">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="77cb6-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="77cb6-120">Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] файл DynamicReconfiguration.sln.</span><span class="sxs-lookup"><span data-stu-id="77cb6-120">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open DynamicReconfiguration.sln.</span></span>  
  
2.  <span data-ttu-id="77cb6-121">Чтобы открыть **обозревателе решений**выберите **обозревателе решений** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="77cb6-121">To open **Solution Explorer**, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="77cb6-122">Нажмите клавишу **F5** или **CTRL + SHIFT + B** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="77cb6-122">Press **F5** or **CTRL+SHIFT+B** in Visual Studio.</span></span>  
  
    1.  <span data-ttu-id="77cb6-123">Если вы хотите автоматически загружались все необходимые проекты при нажатии клавиши **F5**, щелкните правой кнопкой мыши решение и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="77cb6-123">If you would like to auto-launch the necessary projects when you press **F5**, right-click the solution and select **Properties**.</span></span> <span data-ttu-id="77cb6-124">Выберите **запускаемым проектом** узле **общие свойства** в левой области.</span><span class="sxs-lookup"><span data-stu-id="77cb6-124">Select the **Startup Project** node under **Common Properties** in the left pane.</span></span> <span data-ttu-id="77cb6-125">Выберите **несколько запускаемых проектов** кнопку-переключатель и все проекты, чтобы задать **запустить** действие.</span><span class="sxs-lookup"><span data-stu-id="77cb6-125">Select the **Multiple Startup Projects**  radio button and set all of the projects to have the **Start** action.</span></span>  
  
    2.  <span data-ttu-id="77cb6-126">При сборке проекта с **CTRL + SHIFT + B**, необходимо запустить следующие приложения:</span><span class="sxs-lookup"><span data-stu-id="77cb6-126">If you build the project with **CTRL+SHIFT+B**, you must start the following applications:</span></span>  
  
        1.  <span data-ttu-id="77cb6-127">Клиентская часть калькулятора (./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="77cb6-127">Calculator Client (./CalculatorClient/bin/client.exe)</span></span>  
  
        2.  <span data-ttu-id="77cb6-128">Служба -калькулятора (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="77cb6-128">Calculator Service (./CalculatorService/bin/service.exe)</span></span>  
  
        3.  <span data-ttu-id="77cb6-129">Служба калькулятора с маршрутизацией (./RoundingCalcService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="77cb6-129">Routing Calculator Service (./RoundingCalcService/bin/service.exe)</span></span>  
  
        4.  <span data-ttu-id="77cb6-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="77cb6-130">RoutingService (./RoutingService/bin/RoutingService.exe)</span></span>  
  
4.  <span data-ttu-id="77cb6-131">В консольном окне клиентской части калькулятора нажмите клавишу ВВОД для запуска клиента и вызова операций службы «Калькулятор».</span><span class="sxs-lookup"><span data-stu-id="77cb6-131">In the console window of the Calculator Client, press ENTER to start the client and to call the Calculator service operations.</span></span>  
  
     <span data-ttu-id="77cb6-132">Служба маршрутизации передает сообщения поочередно округляющему калькулятору и обычному калькулятору по мере того, как конфигурация маршрутизации динамически меняется каждые пять секунд.</span><span class="sxs-lookup"><span data-stu-id="77cb6-132">The routing service routes messages to the Rounding Calculator and to the regular Calculator alternately as the routing configuration changes dynamically every five seconds.</span></span> <span data-ttu-id="77cb6-133">Вывод в консольном окне клиента различается в зависимости от того, какой из конечных точек служба маршрутизации сконфигурирована отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="77cb6-133">Depending on which endpoint the routing service is configured to send messages to there are different outputs in the client console window.</span></span>  
  
5.  <span data-ttu-id="77cb6-134">Последовательно нажимайте клавишу ВВОД в течение более чем пяти секунд и понаблюдайте за изменением результатов, получаемых от службы.</span><span class="sxs-lookup"><span data-stu-id="77cb6-134">Continue pressing ENTER repeatedly over more than five seconds and observe the change in the results from the service.</span></span>  
  
    1.  <span data-ttu-id="77cb6-135">Далее приведен вывод, получаемый, когда служба маршрутизации настроена для передачи сообщении службе округляющего калькулятора.</span><span class="sxs-lookup"><span data-stu-id="77cb6-135">The following is the output returned if the Router Service is configured to route messages to the Rounding Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  <span data-ttu-id="77cb6-136">Далее приведен вывод, получаемый, когда служба маршрутизации настроена для передачи сообщений обычной службе калькулятора.</span><span class="sxs-lookup"><span data-stu-id="77cb6-136">The following is the output returned if the routing service is configured to route messages to the regular Calculator service.</span></span>  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  <span data-ttu-id="77cb6-137">Служба калькулятора и служба округляющего калькулятора также печатают журнал вызванных операций в соответствующих консольных окнах.</span><span class="sxs-lookup"><span data-stu-id="77cb6-137">The Calculator Service and the Rounding Calculator Service also print out a log of the operations invoked to their respective console windows.</span></span>  
  
7.  <span data-ttu-id="77cb6-138">В окне консоли клиента введите «quit» и нажмите клавишу ВВОД для выхода.</span><span class="sxs-lookup"><span data-stu-id="77cb6-138">In the client console window, type "quit" and press ENTER to exit.</span></span>  
  
8.  <span data-ttu-id="77cb6-139">Нажмите клавишу ВВОД в окнах консоли служб, чтобы завершить службы.</span><span class="sxs-lookup"><span data-stu-id="77cb6-139">Press ENTER in the services console windows to terminate the services.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="77cb6-140">Сценарий</span><span class="sxs-lookup"><span data-stu-id="77cb6-140">Scenario</span></span>  
 <span data-ttu-id="77cb6-141">В этом образце показан маршрутизатор, работающий на основе содержимого и предоставляющий доступ к нескольким типам реализации служб через одну конечную точку.</span><span class="sxs-lookup"><span data-stu-id="77cb6-141">This sample demonstrates the router acting as a content-based router allowing multiple types or implementation of services to be exposed through one endpoint.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="77cb6-142">Реальный сценарий</span><span class="sxs-lookup"><span data-stu-id="77cb6-142">Real World Scenario</span></span>  
 <span data-ttu-id="77cb6-143">Компания Contoso планирует провести виртуализацию всех служб, чтобы сделать общедоступной только одну конечную точку, через которую возможен доступ к нескольким различным типам служб.</span><span class="sxs-lookup"><span data-stu-id="77cb6-143">Contoso wants to virtualize all of their services to expose only one endpoint publicly through which they offer access to multiple different types of services.</span></span> <span data-ttu-id="77cb6-144">В этом случае применяются функции маршрутизации на основе содержимого, чтобы определить назначение для отправки входящих запросов.</span><span class="sxs-lookup"><span data-stu-id="77cb6-144">In this case they utilize the routing service’s content-based routing capabilities to determine where the incoming requests should be sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77cb6-145">См. также</span><span class="sxs-lookup"><span data-stu-id="77cb6-145">See Also</span></span>  
 [<span data-ttu-id="77cb6-146">Образцы размещения AppFabric и сохраняемости</span><span class="sxs-lookup"><span data-stu-id="77cb6-146">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
