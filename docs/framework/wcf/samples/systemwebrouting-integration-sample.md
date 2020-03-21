---
title: Образец интеграции с SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 2f12d80085e3ac27dac8ce80b6bb09f69337bfd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143958"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="b3b93-102">Образец интеграции с SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="b3b93-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="b3b93-103">Этот образец показывает интеграцию уровня размещения с классами в пространстве имен <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="b3b93-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="b3b93-104">Классы в пространстве имен <xref:System.Web.Routing> позволяют приложению использовать URL-адреса, которые не соответствуют непосредственно физическому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b3b93-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="b3b93-105">Использование веб-разгрома позволяет разработчику создавать виртуальные адреса для HTTP, которые затем отображаются обратно к фактическим службам WCF.</span><span class="sxs-lookup"><span data-stu-id="b3b93-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="b3b93-106">Это может быть полезно, когда службу WCF необходимо разместить без обязательного выделения физического файла или ресурса или к службам необходимо получать доступ по URL-адресам, не содержащим файлов, например HTML или ASPX.</span><span class="sxs-lookup"><span data-stu-id="b3b93-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="b3b93-107">Этот образец показывает использование класса <xref:System.Web.Routing.RouteTable> для создания виртуальных URI-адресов, связанных с выполняющимися службами, которые определены в файле global.asax.</span><span class="sxs-lookup"><span data-stu-id="b3b93-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span>

> [!NOTE]
> <span data-ttu-id="b3b93-108">Классы в пространстве имен <xref:System.Web.Routing> работают только со службами, размещаемыми по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="b3b93-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="b3b93-109">Этот пример использует WCF для создания двух `movies` RSS-каналов: корма и `channels` канала.</span><span class="sxs-lookup"><span data-stu-id="b3b93-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="b3b93-110">URL-адреса для активации служб не содержат расширения `Application_Start` и регистрируются в `Global` <xref:System.Web.HttpApplication> методе класса, полученном из класса.</span><span class="sxs-lookup"><span data-stu-id="b3b93-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3b93-111">Этот пример работает только в Интернет-информационных услуг (IIS) 7.0 и позже, как IIS 6.0 использует другой метод для поддержки расширения менее URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="b3b93-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="b3b93-112">Чтобы загрузить этот образец</span><span class="sxs-lookup"><span data-stu-id="b3b93-112">To download this sample</span></span>
  
<span data-ttu-id="b3b93-113">Этот образец уже может быть установлен на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b3b93-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="b3b93-114">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b3b93-114">Check for the following (default) directory before continuing.</span></span>  

`<InstallDrive>:\WF_WCF_Samples`  

 <span data-ttu-id="b3b93-115">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="b3b93-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b3b93-116">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b3b93-116">This sample is located in the following directory.</span></span>  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b3b93-117">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="b3b93-117">To use this sample</span></span>  
  
1. <span data-ttu-id="b3b93-118">Используя Visual Studio, откройте файл WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="b3b93-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="b3b93-119">Нажмите клавишу F5, чтобы выполнить решение и запустить веб-сервер разработки.</span><span class="sxs-lookup"><span data-stu-id="b3b93-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="b3b93-120">Отобразится список каталогов для образца.</span><span class="sxs-lookup"><span data-stu-id="b3b93-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="b3b93-121">Обратите внимание, что файлы с расширением SVC отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="b3b93-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="b3b93-122">В адресной панели `movies` добавьте в URL-адрес, чтобы он считывал `http://localhost:[port]/movies` и нажимать ENTER.</span><span class="sxs-lookup"><span data-stu-id="b3b93-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="b3b93-123">В браузере откроется пакет фильмов.</span><span class="sxs-lookup"><span data-stu-id="b3b93-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="b3b93-124">В адресной панели `channels` добавьте в URL-адрес, чтобы он считывается `http://localhost:[port]/channels` и нажимать ENTER.</span><span class="sxs-lookup"><span data-stu-id="b3b93-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="b3b93-125">В браузере откроется пакет каналов.</span><span class="sxs-lookup"><span data-stu-id="b3b93-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="b3b93-126">Закройте веб-браузер, нажав клавиши ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="b3b93-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="b3b93-127">Если сервер разработки не вышел, нажмите правой кнопкой кнопку значок области уведомлений и выберите **Stop.**</span><span class="sxs-lookup"><span data-stu-id="b3b93-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="b3b93-128">Использование этого образца в случае размещения на IIS</span><span class="sxs-lookup"><span data-stu-id="b3b93-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="b3b93-129">Используя Visual Studio, откройте файл WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="b3b93-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="b3b93-130">Постройте проект, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="b3b93-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="b3b93-131">Создайте веб-приложение в Диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="b3b93-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="b3b93-132">В IIS Manager нажмите правой кнопкой мыши **на веб-сайте по умолчанию** и выберите **Добавить приложение.**</span><span class="sxs-lookup"><span data-stu-id="b3b93-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="b3b93-133">Для **псевдонима,** введите `WebRoutingIntegration`в .</span><span class="sxs-lookup"><span data-stu-id="b3b93-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="b3b93-134">Для **физического пути**выберите папку Службы внутри проекта.</span><span class="sxs-lookup"><span data-stu-id="b3b93-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="b3b93-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b3b93-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="b3b93-136">Запустите приложение, нажав на веб-приложение и выбрав **приложение Manage,** а затем **просмотрите.**</span><span class="sxs-lookup"><span data-stu-id="b3b93-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="b3b93-137">В адресной панели `movies` добавьте в URL-адрес, чтобы он считывается `http://localhost:[port]/movies` и нажимать ENTER.</span><span class="sxs-lookup"><span data-stu-id="b3b93-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="b3b93-138">В браузере откроется пакет фильмов.</span><span class="sxs-lookup"><span data-stu-id="b3b93-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="b3b93-139">В адресной панели `channels` добавьте в URL-адрес, чтобы он считывается `http://localhost:[port]/channels` и нажимать ENTER.</span><span class="sxs-lookup"><span data-stu-id="b3b93-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="b3b93-140">В браузере откроется пакет каналов.</span><span class="sxs-lookup"><span data-stu-id="b3b93-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="b3b93-141">Закройте веб-браузер, нажав клавиши ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="b3b93-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="b3b93-142">Этот образец демонстрирует, что уровень размещения может взаимодействовать с классами в пространстве имен <xref:System.Web.Routing> для маршрутизации запросов служб, размещенных через протокол HTTP.</span><span class="sxs-lookup"><span data-stu-id="b3b93-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3b93-143">Если она настроена на версию 2, необходимо обновить версию пула приложений по умолчанию до .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b3b93-143">You must update the default application pool version to .NET Framework 4 if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3b93-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3b93-144">See also</span></span>

- <span data-ttu-id="b3b93-145">[Образцы размещения и сохраняемости AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b3b93-145">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
