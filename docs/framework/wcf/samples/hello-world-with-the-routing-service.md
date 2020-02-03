---
title: Приветствие средствами служб маршрутизации.
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: ae0615c8cf2fa33f3bb363f77c0d06440b6afc13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743708"
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="8a306-102">Приветствие средствами служб маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="8a306-102">Hello World with the Routing Service</span></span>
<span data-ttu-id="8a306-103">В этом примере демонстрируется служба маршрутизации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8a306-103">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="8a306-104">Служба маршрутизации — это компонент WCF, который позволяет легко включать в приложение маршрутизатор на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="8a306-104">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="8a306-105">Этот пример адаптирует стандартный пример калькулятора WCF для обмена данными с помощью службы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="8a306-105">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="8a306-106">В этом образце клиент ская часть калькулятора настраивается для отправки сообщений в конечную точку, доступ к которой предоставляется маршрутизатором.</span><span class="sxs-lookup"><span data-stu-id="8a306-106">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="8a306-107">Служба маршрутизации настроена на прием всех отправляемых ей сообщений и перенаправление их в конечную точку, которая соответствует службе калькулятора.</span><span class="sxs-lookup"><span data-stu-id="8a306-107">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="8a306-108">Таким образом, сообщения, отправленные клиентом и полученные маршрутизатором, перенаправляются фактической службе калькулятора.</span><span class="sxs-lookup"><span data-stu-id="8a306-108">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="8a306-109">Сообщения от резервной службы калькулятора отправляются назад маршрутизатору, который, в свою очередь, передает их клиенту калькулятора.</span><span class="sxs-lookup"><span data-stu-id="8a306-109">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="8a306-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="8a306-110">To use this sample</span></span>

1. <span data-ttu-id="8a306-111">С помощью Visual Studio 2012 откройте Хеллораутингсервице. sln.</span><span class="sxs-lookup"><span data-stu-id="8a306-111">Using Visual Studio 2012, open HelloRoutingService.sln.</span></span>

2. <span data-ttu-id="8a306-112">Нажмите клавишу F5 или сочетание клавиш CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="8a306-112">Press F5 or CTRL+SHIFT+B.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a306-113">При нажатии F5 автоматически запускается клиентская часть калькулятора.</span><span class="sxs-lookup"><span data-stu-id="8a306-113">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="8a306-114">При нажатии сочетания клавиш CTRL+SHIFT+B (построение) следующие приложения необходимо запустить вручную.</span><span class="sxs-lookup"><span data-stu-id="8a306-114">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>
    >
    > 1. <span data-ttu-id="8a306-115">Клиентская часть калькулятора (./CalculatorClient/bin/client.exe</span><span class="sxs-lookup"><span data-stu-id="8a306-115">Calculator client (./CalculatorClient/bin/client.exe</span></span>
    > 2. <span data-ttu-id="8a306-116">Служба калькулятора (./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="8a306-116">Calculator service (./CalculatorService/bin/service.exe)</span></span>
    > 3. <span data-ttu-id="8a306-117">Служба маршрутизации (./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="8a306-117">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>

3. <span data-ttu-id="8a306-118">Чтобы запустить клиент, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8a306-118">Press ENTER to start the client.</span></span>

     <span data-ttu-id="8a306-119">Вы должны увидеть следующий результат.</span><span class="sxs-lookup"><span data-stu-id="8a306-119">You should see the following output:</span></span>

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="8a306-120">Настраивается в коде или в файле App.config</span><span class="sxs-lookup"><span data-stu-id="8a306-120">Configurable via Code or App.Config</span></span>
 <span data-ttu-id="8a306-121">В поставляемой конфигурации образца поведение маршрутизатора определяется в файле App.config.</span><span class="sxs-lookup"><span data-stu-id="8a306-121">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="8a306-122">Кроме того, можно изменить имя файла App.config на другое, чтобы он не был распознан, и удалить метки комментария с вызова метода ConfigureRouterViaCode().</span><span class="sxs-lookup"><span data-stu-id="8a306-122">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="8a306-123">Поведение маршрутизатора будет одинаковым для обоих методов.</span><span class="sxs-lookup"><span data-stu-id="8a306-123">Either method results in the same behavior from the router.</span></span>

### <a name="scenario"></a><span data-ttu-id="8a306-124">Сценарий</span><span class="sxs-lookup"><span data-stu-id="8a306-124">Scenario</span></span>
 <span data-ttu-id="8a306-125">В этом образце показано, как маршрутизатор пработает в качестве основного средства переноса сообщений.</span><span class="sxs-lookup"><span data-stu-id="8a306-125">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="8a306-126">Служба маршрутизации действует как прозрачный узел-посредник, настроенный передавать сообщения непосредственно заданному набору конечных точек назначения.</span><span class="sxs-lookup"><span data-stu-id="8a306-126">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>

### <a name="real-world-scenario"></a><span data-ttu-id="8a306-127">Реальный сценарий</span><span class="sxs-lookup"><span data-stu-id="8a306-127">Real World Scenario</span></span>
 <span data-ttu-id="8a306-128">В Contoso необходимо повысить уровень гибкости для именования, адресации, конфигурации и обеспечения безопасности его служб.</span><span class="sxs-lookup"><span data-stu-id="8a306-128">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="8a306-129">Для этого базовый цикл обработки сообщений помещается перед службами для выполнения роли открытой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8a306-129">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="8a306-130">Благодаря этому предоставляется возможность обеспечения дополнительного уровня безопасности для фактических служб и упрощается реализация масштабированных решений и управления версиями служб в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="8a306-130">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a306-131">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8a306-131">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8a306-132">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8a306-132">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="8a306-133">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="8a306-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8a306-134">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8a306-134">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="8a306-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8a306-135">See also</span></span>

- <span data-ttu-id="8a306-136">[Примеры размещения и сохраняемости AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8a306-136">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
