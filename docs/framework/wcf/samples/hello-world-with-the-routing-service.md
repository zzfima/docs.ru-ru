---
title: Приветствие средствами служб маршрутизации.
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 881636097cf342de09164804c6df6acfbcd97c45
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="53b6c-102">Приветствие средствами служб маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="53b6c-102">Hello World with the Routing Service</span></span>
<span data-ttu-id="53b6c-103">В этом примере демонстрируется служба маршрутизации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="53b6c-103">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="53b6c-104">Служба маршрутизации является компонентом WCF, который упрощает Включение маршрутизатора на основе содержимого в приложении.</span><span class="sxs-lookup"><span data-stu-id="53b6c-104">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="53b6c-105">В этом примере адаптирует стандартный образец калькулятора WCF для взаимодействия с использованием службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="53b6c-105">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="53b6c-106">В этом образце клиент ская часть калькулятора настраивается для отправки сообщений в конечную точку, доступ к которой предоставляется маршрутизатором.</span><span class="sxs-lookup"><span data-stu-id="53b6c-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="53b6c-107">Служба маршрутизации настроена на прием всех отправляемых ей сообщений и перенаправление их в конечную точку, которая соответствует службе калькулятора.</span><span class="sxs-lookup"><span data-stu-id="53b6c-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="53b6c-108">Таким образом, сообщения, отправленные клиентом и полученные маршрутизатором, перенаправляются фактической службе калькулятора.</span><span class="sxs-lookup"><span data-stu-id="53b6c-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="53b6c-109">Сообщения от резервной службы калькулятора отправляются назад маршрутизатору, который, в свою очередь, передает их клиенту калькулятора.</span><span class="sxs-lookup"><span data-stu-id="53b6c-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="53b6c-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="53b6c-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="53b6c-111">Используйте [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], чтобы открыть файл HelloRoutingService.sln.</span><span class="sxs-lookup"><span data-stu-id="53b6c-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open HelloRoutingService.sln.</span></span>  
  
2.  <span data-ttu-id="53b6c-112">Нажмите клавишу F5 или сочетание клавиш CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="53b6c-112">Press F5 or CTRL+SHIFT+B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53b6c-113">При нажатии F5 автоматически запускается клиентская часть калькулятора.</span><span class="sxs-lookup"><span data-stu-id="53b6c-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="53b6c-114">При нажатии сочетания клавиш CTRL+SHIFT+B (построение) следующие приложения необходимо запустить вручную.</span><span class="sxs-lookup"><span data-stu-id="53b6c-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>  
    >   
    >  1.  <span data-ttu-id="53b6c-115">Клиентская часть калькулятора (./CalculatorClient/bin/client.exe</span><span class="sxs-lookup"><span data-stu-id="53b6c-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>  
    > 2.  <span data-ttu-id="53b6c-116">Служба калькулятора (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="53b6c-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>  
    > 3.  <span data-ttu-id="53b6c-117">Служба маршрутизации (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="53b6c-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>  
  
3.  <span data-ttu-id="53b6c-118">Чтобы запустить клиент, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="53b6c-118">Press ENTER to start the client.</span></span>  
  
     <span data-ttu-id="53b6c-119">Должны выводиться следующие данные:</span><span class="sxs-lookup"><span data-stu-id="53b6c-119">You should see the following output:</span></span>  
  
     <span data-ttu-id="53b6c-120">Add(100,15.99) = 115.99</span><span class="sxs-lookup"><span data-stu-id="53b6c-120">Add(100,15.99) = 115.99</span></span>  
  
     <span data-ttu-id="53b6c-121">Subtract(145,76.54) = 68.46</span><span class="sxs-lookup"><span data-stu-id="53b6c-121">Subtract(145,76.54) = 68.46</span></span>  
  
     <span data-ttu-id="53b6c-122">Multiply(9,81.25) = 731.25</span><span class="sxs-lookup"><span data-stu-id="53b6c-122">Multiply(9,81.25) = 731.25</span></span>  
  
     <span data-ttu-id="53b6c-123">Divide(22,7) = 3.14285714285714</span><span class="sxs-lookup"><span data-stu-id="53b6c-123">Divide(22,7) = 3.14285714285714</span></span>  
  
## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="53b6c-124">Настраивается в коде или в файле App.config</span><span class="sxs-lookup"><span data-stu-id="53b6c-124">Configurable via Code or App.Config</span></span>  
 <span data-ttu-id="53b6c-125">В поставляемой конфигурации образца поведение маршрутизатора определяется в файле App.config.</span><span class="sxs-lookup"><span data-stu-id="53b6c-125">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="53b6c-126">Кроме того, можно изменить имя файла App.config на другое, чтобы он не был распознан, и удалить метки комментария с вызова метода ConfigureRouterViaCode().</span><span class="sxs-lookup"><span data-stu-id="53b6c-126">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="53b6c-127">Поведение маршрутизатора будет одинаковым для обоих методов.</span><span class="sxs-lookup"><span data-stu-id="53b6c-127">Either method results in the same behavior from the router.</span></span>  
  
### <a name="scenario"></a><span data-ttu-id="53b6c-128">Сценарий</span><span class="sxs-lookup"><span data-stu-id="53b6c-128">Scenario</span></span>  
 <span data-ttu-id="53b6c-129">В этом образце показано, как маршрутизатор пработает в качестве основного средства переноса сообщений.</span><span class="sxs-lookup"><span data-stu-id="53b6c-129">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="53b6c-130">Служба маршрутизации действует как прозрачный узел-посредник, настроенный передавать сообщения непосредственно заданному набору конечных точек назначения.</span><span class="sxs-lookup"><span data-stu-id="53b6c-130">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>  
  
### <a name="real-world-scenario"></a><span data-ttu-id="53b6c-131">Реальный сценарий</span><span class="sxs-lookup"><span data-stu-id="53b6c-131">Real World Scenario</span></span>  
 <span data-ttu-id="53b6c-132">В Contoso необходимо повысить уровень гибкости для именования, адресации, конфигурации и обеспечения безопасности его служб.</span><span class="sxs-lookup"><span data-stu-id="53b6c-132">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="53b6c-133">Для этого базовый цикл обработки сообщений помещается перед службами для выполнения роли открытой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="53b6c-133">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="53b6c-134">Благодаря этому предоставляется возможность обеспечения дополнительного уровня безопасности для фактических служб и упрощается реализация масштабированных решений и управления версиями служб в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="53b6c-134">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="53b6c-135">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="53b6c-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="53b6c-136">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="53b6c-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="53b6c-137">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="53b6c-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="53b6c-138">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="53b6c-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="53b6c-139">См. также</span><span class="sxs-lookup"><span data-stu-id="53b6c-139">See Also</span></span>  
 [<span data-ttu-id="53b6c-140">Образцы размещения и сохраняемости образцы</span><span class="sxs-lookup"><span data-stu-id="53b6c-140">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
