---
title: "Образец интеграции с SystemWebRouting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: de8869956a59cb47623dbc4d84763e19d6f181bf
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2018
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="ab717-102">Образец интеграции с SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="ab717-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="ab717-103">Этот образец показывает интеграцию уровня размещения с классами в пространстве имен <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="ab717-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="ab717-104">Классы в пространстве имен <xref:System.Web.Routing> позволяют приложению использовать URL-адреса, которые не соответствуют непосредственно физическому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="ab717-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="ab717-105">С помощью веб-маршрутизации разработчик может создавать виртуальные адреса протокола HTTP, которые затем сопоставляются с действительными службами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab717-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="ab717-106">Это может быть полезно, когда службу WCF необходимо разместить без обязательного выделения физического файла или ресурса или к службам необходимо получать доступ по URL-адресам, не содержащим файлов, например HTML или ASPX.</span><span class="sxs-lookup"><span data-stu-id="ab717-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="ab717-107">Этот образец показывает использование класса <xref:System.Web.Routing.RouteTable> для создания виртуальных URI-адресов, связанных с выполняющимися службами, которые определены в файле global.asax.</span><span class="sxs-lookup"><span data-stu-id="ab717-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
>  <span data-ttu-id="ab717-108">Классы в пространстве имен <xref:System.Web.Routing> работают только со службами, размещаемыми по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="ab717-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="ab717-109">В этом примере используется WCF для создания двух RSS-каналы: `movies` веб-канала и `channels` веб-канала.</span><span class="sxs-lookup"><span data-stu-id="ab717-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="ab717-110">URL-адреса для запуска служб не содержат расширений и зарегистрированы в `Application_Start` метод `Global` класс, производный от <xref:System.Web.HttpApplication> класса.</span><span class="sxs-lookup"><span data-stu-id="ab717-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab717-111">Этот образец работает только в Internet Information Services (IIS) 7.0 и более поздней версии, как службы IIS 6.0 использует другой метод поддержки URL-адресов без расширений.</span><span class="sxs-lookup"><span data-stu-id="ab717-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="ab717-112">Чтобы загрузить этот образец</span><span class="sxs-lookup"><span data-stu-id="ab717-112">To download this sample</span></span>
  
<span data-ttu-id="ab717-113">В этом примере, уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab717-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="ab717-114">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ab717-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="ab717-115">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ab717-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ab717-116">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ab717-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ab717-117">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="ab717-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="ab717-118">Откройте файл WebRoutingIntegration.sln в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ab717-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="ab717-119">Нажмите клавишу F5, чтобы выполнить решение и запустить веб-сервер разработки.</span><span class="sxs-lookup"><span data-stu-id="ab717-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="ab717-120">Отобразится список каталогов для образца.</span><span class="sxs-lookup"><span data-stu-id="ab717-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="ab717-121">Обратите внимание, что файлы с расширением SVC отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ab717-121">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="ab717-122">В адресной строке добавьте `movies` URL-адрес, так что он считывает http://localhost: [порт] / movies и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ab717-122">In the address bar, add `movies` to the URL, so that it reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="ab717-123">В браузере откроется пакет фильмов.</span><span class="sxs-lookup"><span data-stu-id="ab717-123">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="ab717-124">В адресной строке добавьте в URL-адрес слово `channels` (он будет выглядеть как http://localhost:[порт]/channels) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ab717-124">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="ab717-125">В браузере откроется пакет каналов.</span><span class="sxs-lookup"><span data-stu-id="ab717-125">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="ab717-126">Закройте веб-браузер, нажав клавиши ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="ab717-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="ab717-127">Если на сервере разработки не прекратил работу, щелкните правой кнопкой мыши значок области уведомлений и выберите **остановить**.</span><span class="sxs-lookup"><span data-stu-id="ab717-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="ab717-128">Использование этого образца в случае размещения на IIS</span><span class="sxs-lookup"><span data-stu-id="ab717-128">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="ab717-129">Откройте файл WebRoutingIntegration.sln в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ab717-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="ab717-130">Постройте проект, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="ab717-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ab717-131">Создайте веб-приложение в Диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="ab717-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="ab717-132">В диспетчере служб IIS щелкните правой кнопкой мыши **веб-сайт по умолчанию** и выберите **добавить приложение**.</span><span class="sxs-lookup"><span data-stu-id="ab717-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="ab717-133">Для **псевдоним**, введите в `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="ab717-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="ab717-134">Для **физический путь**, укажите служебную папку внутри проекта.</span><span class="sxs-lookup"><span data-stu-id="ab717-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="ab717-135">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab717-135">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="ab717-136">При запуске приложения, щелкнув правой кнопкой мыши веб-приложение и выбрав **управление приложением** и затем **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="ab717-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="ab717-137">В адресной строке добавьте в URL-адрес слово `movies` (он будет выглядеть как http://localhost:[порт]/movies) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ab717-137">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="ab717-138">В браузере откроется пакет фильмов.</span><span class="sxs-lookup"><span data-stu-id="ab717-138">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="ab717-139">В адресной строке добавьте в URL-адрес слово `channels` (он будет выглядеть как http://localhost:[порт]/channels) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="ab717-139">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="ab717-140">В браузере откроется пакет каналов.</span><span class="sxs-lookup"><span data-stu-id="ab717-140">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="ab717-141">Закройте веб-браузер, нажав клавиши ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="ab717-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="ab717-142">Этот образец демонстрирует, что уровень размещения может взаимодействовать с классами в пространстве имен <xref:System.Web.Routing> для маршрутизации запросов служб, размещенных через протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="ab717-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab717-143">Необходимо обновить версию пула приложений по умолчанию [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] Если значение версии 2.</span><span class="sxs-lookup"><span data-stu-id="ab717-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab717-144">См. также</span><span class="sxs-lookup"><span data-stu-id="ab717-144">See Also</span></span>  
 [<span data-ttu-id="ab717-145">Образцы размещения и сохраняемости образцы</span><span class="sxs-lookup"><span data-stu-id="ab717-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
