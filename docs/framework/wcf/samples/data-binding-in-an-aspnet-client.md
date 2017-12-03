---
title: "Привязка данных в клиенте ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18d133b8eb5bef9e6e9152ef856265c1cbe18b51
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="data-binding-in-an-aspnet-client"></a><span data-ttu-id="d456c-102">Привязка данных в клиенте ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d456c-102">Data Binding in an ASP.NET Client</span></span>
<span data-ttu-id="d456c-103">В этом примере показано, как выполнить привязку к данным, обычно возвращаемым службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в приложении веб-форм.</span><span class="sxs-lookup"><span data-stu-id="d456c-103">This sample demonstrates how to bind data returned by a typical [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in a Web Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d456c-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="d456c-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d456c-105">В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="d456c-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="d456c-106">Этот образец состоит из приложения веб-форм, доступного из веб-браузера, и службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенной в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="d456c-106">The sample consists of a client Web Forms application accessible from a browser and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="d456c-107">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="d456c-107">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="d456c-108">Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`.</span><span class="sxs-lookup"><span data-stu-id="d456c-108">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="d456c-109">Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.</span><span class="sxs-lookup"><span data-stu-id="d456c-109">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="d456c-110">На странице ASPX клиента [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] определен веб-элемент управления DataGrid, содержащий графическое представление данных, возвращенных службой.</span><span class="sxs-lookup"><span data-stu-id="d456c-110">On the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] client .aspx page, a DataGrid Web control is defined, which contains the graphical representation of the data returned by the service.</span></span> <span data-ttu-id="d456c-111">Код на странице ASPX вызывает службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для получения данных о погоде и возвращает эти данные в виде массива объектов `WeatherData`.</span><span class="sxs-lookup"><span data-stu-id="d456c-111">Code on the .aspx page calls the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service for weather data and returns the data to an array of `WeatherData` objects.</span></span> <span data-ttu-id="d456c-112">Элемент управления DataGrid задает, откуда он получает свои данные, задавая в свойстве `DataSource` этот массив.</span><span class="sxs-lookup"><span data-stu-id="d456c-112">The DataGrid specifies where to get its data from by setting its `DataSource` property to that array.</span></span> <span data-ttu-id="d456c-113">Привязка данных производится вызовом метода `DataBind` элемента управления DataGrid.</span><span class="sxs-lookup"><span data-stu-id="d456c-113">The data binding occurs with a call to the DataGrid's `DataBind` method.</span></span> <span data-ttu-id="d456c-114">Весь этот код содержится внутри.`aspx`</span><span class="sxs-lookup"><span data-stu-id="d456c-114">All of this code is contained inside the .`aspx`</span></span> <span data-ttu-id="d456c-115">на странице `Page_Load` метод, поэтому каждый раз, когда пользователь обновляет страницу браузера, а данные обновляются в элементе управления DataGrid.</span><span class="sxs-lookup"><span data-stu-id="d456c-115">page's `Page_Load` method, so every time the user refreshes the browser page, the data is updated in the DataGrid.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d456c-116">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d456c-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d456c-117">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d456c-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="d456c-118">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d456c-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="d456c-119">Клиент этого образца представляет собой веб-сайт, работающий под управлением веб-сервера разработки.</span><span class="sxs-lookup"><span data-stu-id="d456c-119">This sample's client is a Web site that runs under a development Web server.</span></span> <span data-ttu-id="d456c-120">Чтобы запустить веб-сервер разработки, введите следующее в командной строке: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`.</span><span class="sxs-lookup"><span data-stu-id="d456c-120">To launch the development Web server, type the following at the command prompt: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`.</span></span> <span data-ttu-id="d456c-121">Затем перейдите по адресу http://localhost:8000/client.</span><span class="sxs-lookup"><span data-stu-id="d456c-121">Then browse to http://localhost:8000/client.</span></span> <span data-ttu-id="d456c-122">Чтобы запустить этот пример на нескольких компьютерах, замените все вхождения `localhost` в файле Web.config клиента именем компьютера сервера.</span><span class="sxs-lookup"><span data-stu-id="d456c-122">To run this sample across computers, replace all references to `localhost` in the client's Web.config file with the computer name of the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d456c-123">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d456c-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d456c-124">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d456c-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d456c-125">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d456c-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d456c-126">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d456c-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a><span data-ttu-id="d456c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d456c-127">See Also</span></span>
