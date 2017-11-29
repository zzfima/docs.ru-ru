---
title: "Образец интеграции с SystemWebRouting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5050834ff01ebb6a25e746d88f7d328ded505cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="f5f91-102">Образец интеграции с SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="f5f91-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="f5f91-103">Этот образец показывает интеграцию уровня размещения с классами в пространстве имен <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="f5f91-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="f5f91-104">Классы в пространстве имен <xref:System.Web.Routing> позволяют приложению использовать URL-адреса, которые не соответствуют непосредственно физическому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="f5f91-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="f5f91-105">С помощью веб-маршрутизации разработчик может создавать виртуальные адреса протокола HTTP, которые затем сопоставляются с действительными службами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5f91-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="f5f91-106">Это может быть полезно, когда службу WCF необходимо разместить без обязательного выделения физического файла или ресурса или к службам необходимо получать доступ по URL-адресам, не содержащим файлов, например HTML или ASPX.</span><span class="sxs-lookup"><span data-stu-id="f5f91-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="f5f91-107">Этот образец показывает использование класса <xref:System.Web.Routing.RouteTable> для создания виртуальных URI-адресов, связанных с выполняющимися службами, которые определены в файле global.asax.</span><span class="sxs-lookup"><span data-stu-id="f5f91-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> <span data-ttu-id="f5f91-108">В данном примере с помощью WCF создаются два RSS-канала: канал `movies` и канал `channels`.</span><span class="sxs-lookup"><span data-stu-id="f5f91-108">For this example, there are two RSS feeds created using WCF: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="f5f91-109">URL-адреса для запуска служб не содержат расширений и зарегистрированы в `Application_Start` метод `Global` класс, производный от <xref:System.Web.HttpApplication.Application_Start> класса.</span><span class="sxs-lookup"><span data-stu-id="f5f91-109">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication.Application_Start> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5f91-110">Классы в пространстве имен <xref:System.Web.Routing> работают только со службами, размещаемыми по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="f5f91-110">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5f91-111">Этот образец работает лишь в [!INCLUDE[iisver](../../../../includes/iisver-md.md)], так как [!INCLUDE[iis60](../../../../includes/iis60-md.md)] использует другой метод поддержки URL-адресов без расширений файлов.</span><span class="sxs-lookup"><span data-stu-id="f5f91-111">This sample only works in [!INCLUDE[iisver](../../../../includes/iisver-md.md)], as [!INCLUDE[iis60](../../../../includes/iis60-md.md)] uses a different method for supporting extension-less URLs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5f91-112">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5f91-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f5f91-113">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f5f91-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f5f91-114">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5f91-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5f91-115">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f5f91-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f5f91-116">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="f5f91-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="f5f91-117">Откройте файл WebRoutingIntegration.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5f91-117">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="f5f91-118">Нажмите клавишу F5, чтобы выполнить решение и запустить веб-сервер разработки.</span><span class="sxs-lookup"><span data-stu-id="f5f91-118">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="f5f91-119">Отобразится список каталогов для образца.</span><span class="sxs-lookup"><span data-stu-id="f5f91-119">A directory listing for the sample appears.</span></span> <span data-ttu-id="f5f91-120">Обратите внимание, что файлы с расширением SVC отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="f5f91-120">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="f5f91-121">В адресной строке добавьте в URL-адрес слово `movies` (он будет выглядеть как http://localhost:[порт]/movies) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f5f91-121">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="f5f91-122">В браузере откроется пакет фильмов.</span><span class="sxs-lookup"><span data-stu-id="f5f91-122">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="f5f91-123">В адресной строке добавьте в URL-адрес слово `channels` (он будет выглядеть как http://localhost:[порт]/channels) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f5f91-123">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="f5f91-124">В браузере откроется пакет каналов.</span><span class="sxs-lookup"><span data-stu-id="f5f91-124">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="f5f91-125">Закройте веб-браузер, нажав клавиши ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="f5f91-125">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="f5f91-126">Если на сервере разработки не прекратил работу, щелкните правой кнопкой мыши значок области уведомлений и выберите **остановить**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-126">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="f5f91-127">Использование этого образца в случае размещения на IIS</span><span class="sxs-lookup"><span data-stu-id="f5f91-127">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="f5f91-128">Откройте файл WebRoutingIntegration.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5f91-128">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="f5f91-129">Постройте проект, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="f5f91-129">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f5f91-130">Создайте веб-приложение в Диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="f5f91-130">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="f5f91-131">В диспетчере служб IIS щелкните правой кнопкой мыши **веб-сайт по умолчанию** и выберите **добавить приложение**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-131">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="f5f91-132">Для **псевдоним**, введите в `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="f5f91-132">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="f5f91-133">Для **физический путь**, укажите служебную папку внутри проекта.</span><span class="sxs-lookup"><span data-stu-id="f5f91-133">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="f5f91-134">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-134">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="f5f91-135">При запуске приложения, щелкнув правой кнопкой мыши веб-приложение и выбрав **управление приложением** и затем **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="f5f91-135">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="f5f91-136">В адресной строке добавьте в URL-адрес слово `movies` (он будет выглядеть как http://localhost:[порт]/movies) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f5f91-136">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="f5f91-137">В браузере откроется пакет фильмов.</span><span class="sxs-lookup"><span data-stu-id="f5f91-137">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="f5f91-138">В адресной строке добавьте в URL-адрес слово `channels` (он будет выглядеть как http://localhost:[порт]/channels) и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f5f91-138">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="f5f91-139">В браузере откроется пакет каналов.</span><span class="sxs-lookup"><span data-stu-id="f5f91-139">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="f5f91-140">Закройте веб-браузер, нажав клавиши ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="f5f91-140">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="f5f91-141">Этот образец демонстрирует, что уровень размещения может взаимодействовать с классами в пространстве имен <xref:System.Web.Routing> для маршрутизации запросов служб, размещенных через протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="f5f91-141">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5f91-142">Обновите версию пула приложений по умолчанию до [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], если установлена версия 2.</span><span class="sxs-lookup"><span data-stu-id="f5f91-142">Please update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f91-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f5f91-143">See Also</span></span>  
 [<span data-ttu-id="f5f91-144">Образцы размещения и сохраняемости образцы</span><span class="sxs-lookup"><span data-stu-id="f5f91-144">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
