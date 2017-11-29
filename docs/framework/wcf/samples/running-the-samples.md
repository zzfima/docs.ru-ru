---
title: "Выполнение примеров Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3cc4417d1781975663b92b777ecff8789372848
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="running-the-windows-communication-foundation-samples"></a><span data-ttu-id="1923a-102">Выполнение примеров Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1923a-102">Running the Windows Communication Foundation Samples</span></span>
<span data-ttu-id="1923a-103">Примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] могут выполняться на одном или нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="1923a-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples can be run in a single-machine or cross-machine configuration.</span></span> <span data-ttu-id="1923a-104">После передачи примеры готовы к выполнению на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1923a-104">As supplied, the samples are ready for running on a single machine.</span></span> <span data-ttu-id="1923a-105">При выполнении на нескольких компьютерах необходимо изменить параметры файла конфигурации примера.</span><span class="sxs-lookup"><span data-stu-id="1923a-105">In a cross-machine configuration, it is necessary to modify a sample's configuration file settings.</span></span> <span data-ttu-id="1923a-106">В следующих процедурах объясняется, как выполнить пример на одном компьютере или на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="1923a-106">The following procedures explain how to run a sample in same-machine and cross-machine configurations.</span></span> <span data-ttu-id="1923a-107">Обратите внимание, что шаги, выполняемые для служб, размещенных в службах IIS, и шаги для резидентных примеров, отличаются.</span><span class="sxs-lookup"><span data-stu-id="1923a-107">Note that there are variations in the steps for services hosted in Internet Information Services (IIS) and the self-hosted samples.</span></span> <span data-ttu-id="1923a-108">Большинство примеров размещаются в службах IIS; чтобы определить, как размещается пример, см. сведения в файле Readme.</span><span class="sxs-lookup"><span data-stu-id="1923a-108">Most samples are hosted in IIS; see the sample readme information to determine how it is hosted.</span></span>  
  
 <span data-ttu-id="1923a-109">В [!INCLUDE[wv](../../../../includes/wv-md.md)] образцы, которые не размещаются в службах IIS, должны иметь более высокий уровень привилегий при регистрации прослушивателя в Http.sys.</span><span class="sxs-lookup"><span data-stu-id="1923a-109">On [!INCLUDE[wv](../../../../includes/wv-md.md)], samples that are not hosted in IIS require elevated privileges to register a listener with Http.sys.</span></span> <span data-ttu-id="1923a-110">Используйте средство Httpcfg.exe для регистрации адреса ожидания передачи данных службы, работающей под учетной записью службы, или запустите службу из командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="1923a-110">Use Httpcfg.exe to register the service's listening addresses with the account the service is running under, or launch the service from a command prompt running with administrator privileges.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1923a-111">До построения или выполнением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] образцы, убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1923a-111">Before building or running any of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples, be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="1923a-112">Запуск образца на том же компьютере</span><span class="sxs-lookup"><span data-stu-id="1923a-112">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="1923a-113">Если служба размещена в IIS, убедитесь в наличии доступа к службе с помощью браузера, введя следующий адрес: http://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="1923a-113">If the service is hosted by IIS, ensure that you can access the service using a browser by entering the following address: http://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="1923a-114">Должна отобразиться страница подтверждения.</span><span class="sxs-lookup"><span data-stu-id="1923a-114">A confirmation page should be displayed in response.</span></span> <span data-ttu-id="1923a-115">Если страница подтверждения не отображается, см. раздел [советы по устранению неполадок](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="1923a-115">If the confirmation page is not displayed, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
2.  <span data-ttu-id="1923a-116">Если служба является резидентной, запустите программу Service.exe из папки \service\bin\ в языковой папке.</span><span class="sxs-lookup"><span data-stu-id="1923a-116">If the service is self-hosted, run Service.exe from \service\bin, from under the language-specific folder.</span></span> <span data-ttu-id="1923a-117">Действия службы отображаются в окне консоли службы.</span><span class="sxs-lookup"><span data-stu-id="1923a-117">Service activity is displayed on the service console window.</span></span>  
  
3.  <span data-ttu-id="1923a-118">Запустите Client.exe из \client\bin\\, \service\bin\ в языковой папке.</span><span class="sxs-lookup"><span data-stu-id="1923a-118">Run Client.exe from \client\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="1923a-119">Действия клиента отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="1923a-119">Client activity is displayed on the client console window.</span></span>  
  
4.  <span data-ttu-id="1923a-120">Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="1923a-120">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="1923a-121">Выполнение примера на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="1923a-121">To run the sample across machines</span></span>  
  
1.  <span data-ttu-id="1923a-122">Служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="1923a-122">If the service is hosted in IIS:</span></span>  
  
    1.  <span data-ttu-id="1923a-123">На компьютере службы создайте виртуальный каталог с именем ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="1923a-123">On the service machine, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="1923a-124">В пакетный файл Setupvroot.bat с [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) может использоваться для создания каталога диска и виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="1923a-124">The batch file Setupvroot.bat included with [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) can be used to create the disk directory and virtual directory.</span></span>  
  
    2.  <span data-ttu-id="1923a-125">Скопируйте файлы программы службы из каталога %SystemDrive%\Inetpub\wwwroot\servicemodelsamples в виртуальный каталог ServiceModelSamples на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="1923a-125">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service machine.</span></span> <span data-ttu-id="1923a-126">Убедитесь, что включены все файлы каталога \bin.</span><span class="sxs-lookup"><span data-stu-id="1923a-126">Ensure that you include the files in the \bin directory.</span></span>  
  
    3.  <span data-ttu-id="1923a-127">Убедитесь, что доступ к службе с клиентского компьютера можно получить из браузера.</span><span class="sxs-lookup"><span data-stu-id="1923a-127">Test that you can access the service from the client machine using a browser.</span></span>  
  
     <span data-ttu-id="1923a-128">Служба является резидентной.</span><span class="sxs-lookup"><span data-stu-id="1923a-128">If the service is self-hosted:</span></span>  
  
    1.  <span data-ttu-id="1923a-129">Создайте каталог для хранения файлов службы на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="1923a-129">On the service machine, create a directory to hold the service files.</span></span>  
  
    2.  <span data-ttu-id="1923a-130">Скопируйте на компьютер службы файлы программы службы из папки \service\bin\ в языковой папке.</span><span class="sxs-lookup"><span data-stu-id="1923a-130">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service machine.</span></span>  
  
    3.  <span data-ttu-id="1923a-131">В файле конфигурации службы измените значение адреса определения конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="1923a-131">In the service configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="1923a-132">Замените любые ссылки на "localhost" в адресе полным именем домена.</span><span class="sxs-lookup"><span data-stu-id="1923a-132">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
    4.  <span data-ttu-id="1923a-133">Запустите программу Service.exe из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1923a-133">Launch Service.exe from a command prompt.</span></span>  
  
2.  <span data-ttu-id="1923a-134">Скопируйте на клиентский компьютер файлы программы клиента из папки \client\bin\ в языковой папке.</span><span class="sxs-lookup"><span data-stu-id="1923a-134">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machine.</span></span>  
  
3.  <span data-ttu-id="1923a-135">Задайте адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1923a-135">Set the endpoint address.</span></span>  
  
    1.  <span data-ttu-id="1923a-136">Если не удается запустить службу из учетной записи домена, откройте файл конфигурации клиента и измените значение адреса определения конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="1923a-136">If the service is not running under a domain account, open the client configuration file and change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="1923a-137">Замените любые ссылки на "localhost" в адресе полным именем домена.</span><span class="sxs-lookup"><span data-stu-id="1923a-137">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
    2.  <span data-ttu-id="1923a-138">Если служба выполняется в учетной записи домена, заново создайте конфигурацию клиента, выполнив Svcutil.exe относительно службы.</span><span class="sxs-lookup"><span data-stu-id="1923a-138">If the service is running under a domain account, regenerate the client configuration by running Svcutil.exe against the service.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1923a-139">см. под управлением Svcutil.exe, [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1923a-139"> running Svcutil.exe, see [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="1923a-140">Используйте созданный файл вместо файла конфигурации в примере.</span><span class="sxs-lookup"><span data-stu-id="1923a-140">Use the generated file instead of the configuration file in the sample.</span></span> <span data-ttu-id="1923a-141">В созданном файле конфигурации содержатся дополнительные данные идентификации (и содержатся все параметры, необходимые для подключения к конечной точке службы, даже если они являются параметрами по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1923a-141">The generated configuration file has additional identity information, and contains all settings necessary to connect to the service endpoint even though they are the default settings.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1923a-142">сведения об удостоверении, в разделе [удостоверения службы и проверки подлинности](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md), и [ \<удостоверение >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md).</span><span class="sxs-lookup"><span data-stu-id="1923a-142"> identity information, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md), and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md).</span></span>  
  
4.  <span data-ttu-id="1923a-143">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="1923a-143">On the client machine, launch Client.exe from a command prompt.</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="1923a-144">Отладка службы</span><span class="sxs-lookup"><span data-stu-id="1923a-144">To debug a service</span></span>  
  
1.  <span data-ttu-id="1923a-145">Сборки решения (клиент и служба) с помощью **построения** меню или сочетание клавиш CTRL + SHIFT + B.</span><span class="sxs-lookup"><span data-stu-id="1923a-145">Build the solution (both client and service) using the **Build** menu or CTRL+SHIFT+B.</span></span>  
  
2.  <span data-ttu-id="1923a-146">Служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="1923a-146">If the service is hosted in IIS:</span></span>  
  
    1.  <span data-ttu-id="1923a-147">Активируйте службу с помощью браузера: введите в адресной строке http://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="1923a-147">Activate the service using a browser by entering the address http://localhost/servicemodelsamples/service.svc.</span></span>  
  
    2.  <span data-ttu-id="1923a-148">В решении, выберите **отладки** меню и **присоединиться к процессу** элемента меню.</span><span class="sxs-lookup"><span data-stu-id="1923a-148">In the solution, choose the **Debug** menu and the **Attach to Process** menu item.</span></span>  
  
    3.  <span data-ttu-id="1923a-149">Выберите **Показать процессы всех пользователей** флажок.</span><span class="sxs-lookup"><span data-stu-id="1923a-149">Select the **Show processes from all users** check box.</span></span>  
  
    4.  <span data-ttu-id="1923a-150">Выберите рабочий процесс ведущего приложения W3wp.exe для отладки (в Windows XP выберите ASPNet_wp.exe).</span><span class="sxs-lookup"><span data-stu-id="1923a-150">Select the host worker process W3wp.exe to debug (select ASPNet_wp.exe on Windows XP).</span></span>  
  
3.  <span data-ttu-id="1923a-151">Теперь можно задать точки останова в коде службы и включить точки останова в исключениях.</span><span class="sxs-lookup"><span data-stu-id="1923a-151">You can now set breakpoints in the service code and enable breakpoints on exceptions.</span></span>  
  
4.  <span data-ttu-id="1923a-152">Щелкните правой кнопкой мыши элемент клиентского проекта и выберите **отладки**, **запустить новый экземпляр**.</span><span class="sxs-lookup"><span data-stu-id="1923a-152">Right-click the client project item and choose **Debug**, **Start new instance**.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="1923a-153">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="1923a-153">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="1923a-154">Если служба размещается в службах IIS в целях безопасности, удалите определение виртуального каталога и разрешения, предоставленные на шагах установки, по завершении работы с примерами.</span><span class="sxs-lookup"><span data-stu-id="1923a-154">If the service is hosted in IIS for security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1923a-155">См. также</span><span class="sxs-lookup"><span data-stu-id="1923a-155">See Also</span></span>  
 [<span data-ttu-id="1923a-156">Построение образцов Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1923a-156">Building the Windows Communication Foundation Samples</span></span>](../../../../docs/framework/wcf/samples/building-the-samples.md)  
 [<span data-ttu-id="1923a-157">Выполнение примеров в рабочей группе и на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="1923a-157">Running the Samples in a Workgroup and Across Machines</span></span>](http://msdn.microsoft.com/en-us/a451a525-e7ce-452d-9da9-620221260113)  
 [<span data-ttu-id="1923a-158">Советы по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="1923a-158">Troubleshooting Tips</span></span>](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b)
