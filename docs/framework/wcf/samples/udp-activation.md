---
title: "Активация UDP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32c452042ffee0a09143042900d24b7429234bec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="udp-activation"></a><span data-ttu-id="33534-102">Активация UDP</span><span class="sxs-lookup"><span data-stu-id="33534-102">UDP Activation</span></span>
<span data-ttu-id="33534-103">Этот пример построен на [транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) образца.</span><span class="sxs-lookup"><span data-stu-id="33534-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="33534-104">Он расширяет [транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) пример поддержки активацию с помощью службы активации процессов Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="33534-104">It extends the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample to support process activation using the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="33534-105">Образец состоит из трех основных частей:</span><span class="sxs-lookup"><span data-stu-id="33534-105">The sample consists of three major pieces:</span></span>  
  
-   <span data-ttu-id="33534-106">Активатор протокола UDP - автономный процесс, получающий сообщения UDP от лица приложений, подлежащих активации.</span><span class="sxs-lookup"><span data-stu-id="33534-106">A UDP Protocol Activator, a standalone process that receives UDP messages on behalf of applications that are to be activated.</span></span>  
  
-   <span data-ttu-id="33534-107">Клиент, использующий пользовательский транспорт UDP для отправки сообщений.</span><span class="sxs-lookup"><span data-stu-id="33534-107">A client that uses the UDP custom transport to send messages.</span></span>  
  
-   <span data-ttu-id="33534-108">Служба (размещенная в рабочем процессе, активированном службой WAS), получающая сообщения по пользовательскому транспорту UDP.</span><span class="sxs-lookup"><span data-stu-id="33534-108">A service (hosted in a worker process activated by WAS) that receives messages over the UDP custom transport.</span></span>  
  
## <a name="udp-protocol-activator"></a><span data-ttu-id="33534-109">Активатор протокола UDP</span><span class="sxs-lookup"><span data-stu-id="33534-109">UDP Protocol Activator</span></span>  
 <span data-ttu-id="33534-110">Активатор протокола UDP представляет собой мост между клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33534-110">The UDP Protocol Activator is a bridge between the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="33534-111">Он обеспечивает передачу данных через протокол UDP на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="33534-111">It provides data communication through the UDP protocol at the transport layer.</span></span> <span data-ttu-id="33534-112">У него две основные функции.</span><span class="sxs-lookup"><span data-stu-id="33534-112">It has two major functions:</span></span>  
  
-   <span data-ttu-id="33534-113">Адаптер прослушивателя WAS (LA), работающий совместно со службой WAS для активирования процессов в ответ на входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="33534-113">WAS Listener Adapter (LA), which collaborates with WAS to activate processes in response to incoming messages.</span></span>  
  
-   <span data-ttu-id="33534-114">Прослушиватель протокола UDP, который принимает сообщения UDP от лица приложений, подлежащих активации.</span><span class="sxs-lookup"><span data-stu-id="33534-114">UDP Protocol Listener, which accepts UDP messages on behalf of applications that are to be activated.</span></span>  
  
 <span data-ttu-id="33534-115">Активатор должен работать как автономная программа на компьютере сервера.</span><span class="sxs-lookup"><span data-stu-id="33534-115">The activator must be running as a standalone program on the server machine.</span></span> <span data-ttu-id="33534-116">Обычно адаптеры прослушивателя WAS (такие как NetTcpActivator и NetPipeActivator) реализуются в долговременных службах Windows.</span><span class="sxs-lookup"><span data-stu-id="33534-116">Normally, WAS listener adapters (such as the NetTcpActivator and the NetPipeActivator) are implemented in long-running Windows services.</span></span> <span data-ttu-id="33534-117">Однако для простоты и ясности в данном образце активатор протокола реализован как автономное приложение.</span><span class="sxs-lookup"><span data-stu-id="33534-117">However, for simplicity and clarity, this sample implements the protocol activator as a standalone application.</span></span>  
  
### <a name="was-listener-adapter"></a><span data-ttu-id="33534-118">Адаптер прослушивателя WAS</span><span class="sxs-lookup"><span data-stu-id="33534-118">WAS Listener Adapter</span></span>  
 <span data-ttu-id="33534-119">Адаптер прослушивателя WAS для протокола UDP реализован в классе `UdpListenerAdapter`.</span><span class="sxs-lookup"><span data-stu-id="33534-119">The WAS Listener Adapter for UDP is implemented in the `UdpListenerAdapter` class.</span></span> <span data-ttu-id="33534-120">Именно этот модуль во взаимодействии со службой WAS выполняет активацию приложения для протокола UDP.</span><span class="sxs-lookup"><span data-stu-id="33534-120">It is the module that interacts with WAS to perform application activation for the UDP protocol.</span></span> <span data-ttu-id="33534-121">Это производится путем вызова следующих интерфейсов Webhost API:</span><span class="sxs-lookup"><span data-stu-id="33534-121">This is achieved by calling the following Webhost APIs:</span></span>  
  
-   `WebhostRegisterProtocol`  
  
-   `WebhostUnregisterProtocol`  
  
-   `WebhostOpenListenerChannelInstance`  
  
-   `WebhostCloseAllListenerChannelInstances`  
  
 <span data-ttu-id="33534-122">После исходного вызова `WebhostRegisterProtocol` адаптер прослушивателя получает обратный вызов `ApplicationCreated` от службы WAS для всех приложений, зарегистрированных в applicationHost.config (расположен в %windir%\system32\inetsrv).</span><span class="sxs-lookup"><span data-stu-id="33534-122">After initially calling `WebhostRegisterProtocol`, the listener adapter receives the callback `ApplicationCreated` from WAS for all of the applications registered in applicationHost.config (located in %windir%\system32\inetsrv).</span></span> <span data-ttu-id="33534-123">В этом образце обрабатываются только приложения с включенным протоколом UDP (с ИД протокола "net.udp").</span><span class="sxs-lookup"><span data-stu-id="33534-123">In this sample, we only handle the applications with the UDP protocol (with the protocol id as "net.udp") enabled.</span></span> <span data-ttu-id="33534-124">Другие реализации могут выполнять эту обработку по-другому, если такие реализацию реагируют на динамические изменения конфигурации приложения (например, переход приложения из отключенного состояния во включенное).</span><span class="sxs-lookup"><span data-stu-id="33534-124">Other implementations may handle this differently if such implementations respond to dynamic configuration changes to the application (for example, an application transition from disabled to enabled).</span></span>  
  
 <span data-ttu-id="33534-125">Получение обратного вызова `ConfigManagerInitializationCompleted` показывает, что служба WAS завершила все уведомления для инициализации протокола.</span><span class="sxs-lookup"><span data-stu-id="33534-125">When the callback `ConfigManagerInitializationCompleted` is received, it indicates that WAS has finished all of the notifications for the initialization of the protocol.</span></span> <span data-ttu-id="33534-126">На этом этапе прослушиватель готов к обработке запросов активации.</span><span class="sxs-lookup"><span data-stu-id="33534-126">At this time, the listener adapter is ready to process activation requests.</span></span>  
  
 <span data-ttu-id="33534-127">При поступлении нового запроса, который является первым для приложения, адаптер прослушивателя вызывает `WebhostOpenListenerChannelInstance` в WAS, запуская рабочий процесс, если он еще не запущен.</span><span class="sxs-lookup"><span data-stu-id="33534-127">When a new request comes in the first time for an application, the listener adapter calls `WebhostOpenListenerChannelInstance` into WAS, which starts the worker process if it is not started yet.</span></span> <span data-ttu-id="33534-128">Затем загружаются обработчики протокола, и можно начинать обмен данными между адаптером прослушивателя и виртуальным приложением.</span><span class="sxs-lookup"><span data-stu-id="33534-128">Then the protocol handlers are loaded and the communication between the listener adapter and the virtual application can start.</span></span>  
  
 <span data-ttu-id="33534-129">Адаптер прослушивателя регистрируется в %SystemRoot%\System32\inetsrv\ApplicationHost.config в <`listenerAdapters`> статьи следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33534-129">The listener adapter is registered in the %SystemRoot%\System32\inetsrv\ApplicationHost.config in the <`listenerAdapters`> section as following:</span></span>  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a><span data-ttu-id="33534-130">Прослушиватель протокола</span><span class="sxs-lookup"><span data-stu-id="33534-130">Protocol Listener</span></span>  
 <span data-ttu-id="33534-131">Прослушиватель протокола UDP представляет собой модуль внутри активатора протокола, который ожидает передачи данных на конечной точке UDP от лица виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="33534-131">The UDP protocol listener is a module inside the protocol activator that listens at a UDP endpoint on behalf of the virtual application.</span></span> <span data-ttu-id="33534-132">Он реализован в классе `UdpSocketListener`.</span><span class="sxs-lookup"><span data-stu-id="33534-132">It is implemented in the class `UdpSocketListener`.</span></span> <span data-ttu-id="33534-133">Конечная точка представлена как `IPEndpoint`, номер порта для которой извлекается из привязки протокола для сайта.</span><span class="sxs-lookup"><span data-stu-id="33534-133">The endpoint is represented as `IPEndpoint` for which the port number is extracted from the binding of the protocol for the site.</span></span>  
  
### <a name="control-service"></a><span data-ttu-id="33534-134">Служба управления</span><span class="sxs-lookup"><span data-stu-id="33534-134">Control Service</span></span>  
 <span data-ttu-id="33534-135">В данном образце для взаимодействия активатора и рабочего процесса WAS используется [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33534-135">In this sample, we use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to communicate between the activator and the WAS worker process.</span></span> <span data-ttu-id="33534-136">Служба, находящаяся в активаторе, называется службой управления.</span><span class="sxs-lookup"><span data-stu-id="33534-136">The service that resides in the activator is called the Control Service.</span></span>  
  
## <a name="protocol-handlers"></a><span data-ttu-id="33534-137">Обработчики протоколов</span><span class="sxs-lookup"><span data-stu-id="33534-137">Protocol Handlers</span></span>  
 <span data-ttu-id="33534-138">После того как адаптер прослушивателя вызывает `WebhostOpenListenerChannelInstance`, диспетчер процесса WAS запускает рабочий процесс, если он еще не запущен.</span><span class="sxs-lookup"><span data-stu-id="33534-138">After the listener adapter calls `WebhostOpenListenerChannelInstance`, the WAS process manager starts the worker process if it is not started.</span></span> <span data-ttu-id="33534-139">Затем диспетчер приложения внутри рабочего процесса загружает обработчик протокола процесса (PPH) UDP с запросом этого `ListenerChannelId`.</span><span class="sxs-lookup"><span data-stu-id="33534-139">The application manager inside the worker process then loads the UDP Process Protocol Handler (PPH) with the request for that `ListenerChannelId`.</span></span> <span data-ttu-id="33534-140">PPH в вызывает `IAdphManager`.`StartAppDomainProtocolListenerChannel`</span><span class="sxs-lookup"><span data-stu-id="33534-140">The PPH in turns calls `IAdphManager`.`StartAppDomainProtocolListenerChannel`</span></span> <span data-ttu-id="33534-141">Чтобы запустить обработчик протокола AppDomain (ADPH) UDP.</span><span class="sxs-lookup"><span data-stu-id="33534-141">to start the UDP AppDomain Protocol Handler (ADPH).</span></span>  
  
## <a name="hostedudptransportconfiguration"></a><span data-ttu-id="33534-142">HostedUDPTransportConfiguration</span><span class="sxs-lookup"><span data-stu-id="33534-142">HostedUDPTransportConfiguration</span></span>  
 <span data-ttu-id="33534-143">Информация регистрируется в файле Web.config следующим образом:</span><span class="sxs-lookup"><span data-stu-id="33534-143">The information is registered in the Web.config as follows:</span></span>  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a><span data-ttu-id="33534-144">Специальная настройка для этого примера</span><span class="sxs-lookup"><span data-stu-id="33534-144">Special Setup for This Sample</span></span>  
 <span data-ttu-id="33534-145">Этот образец может быть построен и запущен только в ОС Windows Vista, Windows Server 2008 или Windows 7.</span><span class="sxs-lookup"><span data-stu-id="33534-145">This sample can be only built and run on Windows Vista, Windows Server 2008, or Windows 7.</span></span> <span data-ttu-id="33534-146">Для запуска этого примера необходимо сначала правильно установить все компоненты.</span><span class="sxs-lookup"><span data-stu-id="33534-146">To run the sample, you must first get all of the components set up correctly.</span></span> <span data-ttu-id="33534-147">Установите образец в соответствии с приведенными ниже шагами.</span><span class="sxs-lookup"><span data-stu-id="33534-147">Use the following steps to install the sample.</span></span>  
  
#### <a name="to-set-up-this-sample"></a><span data-ttu-id="33534-148">Настройка этого образца</span><span class="sxs-lookup"><span data-stu-id="33534-148">To set up this sample</span></span>  
  
1.  <span data-ttu-id="33534-149">Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="33534-149">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="33534-150">Постройте проект в ОС Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="33534-150">Build the project on Windows Vista.</span></span> <span data-ttu-id="33534-151">После компиляции на этапе за построением также выполняются следующие операции.</span><span class="sxs-lookup"><span data-stu-id="33534-151">After compilation, it also performs the following operations in the post-build phase:</span></span>  
  
    -   <span data-ttu-id="33534-152">Устанавливается привязка UDP на сайт "Веб-узел по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="33534-152">Installs the UDP binding to the site "Default Web Site".</span></span>  
  
    -   <span data-ttu-id="33534-153">Создается виртуальное приложение "ServiceModelSamples", указывающее по физическому пути: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span><span class="sxs-lookup"><span data-stu-id="33534-153">Creates the virtual application "ServiceModelSamples" to point to the physical path: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span></span>  
  
    -   <span data-ttu-id="33534-154">Также включается протокол "net.udp" для данного виртуального приложения.</span><span class="sxs-lookup"><span data-stu-id="33534-154">It also enables "net.udp" protocol for this virtual application.</span></span>  
  
3.  <span data-ttu-id="33534-155">Запустите приложение пользовательского интерфейса "WasNetActivator.exe".</span><span class="sxs-lookup"><span data-stu-id="33534-155">Start the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="33534-156">Нажмите кнопку **установки** , проверьте следующие флажки и нажмите кнопку **установить** установить их:</span><span class="sxs-lookup"><span data-stu-id="33534-156">Click the **Setup** tab, check the following check boxes and then click **Install** to install them:</span></span>  
  
    -   <span data-ttu-id="33534-157">Адаптер прослушивателя UDP</span><span class="sxs-lookup"><span data-stu-id="33534-157">UDP Listener Adapter</span></span>  
  
    -   <span data-ttu-id="33534-158">Обработчики протокола UDP</span><span class="sxs-lookup"><span data-stu-id="33534-158">UDP Protocol Handlers</span></span>  
  
4.  <span data-ttu-id="33534-159">Нажмите кнопку **активации** вкладке приложение пользовательского интерфейса «WasNetActivator.exe».</span><span class="sxs-lookup"><span data-stu-id="33534-159">Click the **Activation** tab of the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="33534-160">Нажмите кнопку **запустить** кнопку для запуска адаптера прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="33534-160">Click the **Start** button to start the listener adapter.</span></span> <span data-ttu-id="33534-161">Теперь все готово для запуска программы.</span><span class="sxs-lookup"><span data-stu-id="33534-161">Now you are ready to run the program.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33534-162">Завершив работу с этим примером, необходимо запустить файл Cleanup.bat, чтобы удалить привязку net.udp с сайта "Веб-узел по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="33534-162">When you are finished with this sample, you must run Cleanup.bat to remove the net.udp binding from the "Default Web Site".</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="33534-163">Использование примера</span><span class="sxs-lookup"><span data-stu-id="33534-163">Sample Usage</span></span>  
 <span data-ttu-id="33534-164">После компиляции создаются четыре различных двоичных файла.</span><span class="sxs-lookup"><span data-stu-id="33534-164">After compilation, there are four different binaries generated:</span></span>  
  
-   <span data-ttu-id="33534-165">Client.exe: код клиента.</span><span class="sxs-lookup"><span data-stu-id="33534-165">Client.exe: The client code.</span></span> <span data-ttu-id="33534-166">Файл App.config компилируется в файл конфигурации клиента Client.exe.config.</span><span class="sxs-lookup"><span data-stu-id="33534-166">The App.config is compiled into the client configuration file Client.exe.config.</span></span>  
  
-   <span data-ttu-id="33534-167">UDPActivation.dll: библиотека, содержащая все основные реализации UDP.</span><span class="sxs-lookup"><span data-stu-id="33534-167">UDPActivation.dll: the library that contains all of the major UDP implementations.</span></span>  
  
-   <span data-ttu-id="33534-168">Service.dll: код службы.</span><span class="sxs-lookup"><span data-stu-id="33534-168">Service.dll: The service code.</span></span> <span data-ttu-id="33534-169">Он копируется в каталог \bin виртуального приложения ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="33534-169">This is copied to the \bin directory of the virtual application ServiceModelSamples.</span></span> <span data-ttu-id="33534-170">Файл службы имеет имя Service.svc, а файл конфигурации - Web.config. После компиляции они копируются в следующее местоположение: %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="33534-170">The service file is Service.svc and the configuration file is Web.config. After compilation, they are copied to the following location: %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.</span></span>  
  
-   <span data-ttu-id="33534-171">WasNetActivator: программа активатора UDP.</span><span class="sxs-lookup"><span data-stu-id="33534-171">WasNetActivator: The UDP activator program.</span></span>  
  
-   <span data-ttu-id="33534-172">Убедитесь, что все обязательные элементы правильно установлены.</span><span class="sxs-lookup"><span data-stu-id="33534-172">Ensure that all of the required pieces are installed correctly.</span></span> <span data-ttu-id="33534-173">Следующие шаги показывают, как запустить образец:</span><span class="sxs-lookup"><span data-stu-id="33534-173">The following steps show how to run the sample:</span></span>  
  
1.  <span data-ttu-id="33534-174">Убедитесь, что запущены следующие службы Windows:</span><span class="sxs-lookup"><span data-stu-id="33534-174">Ensure that the following Windows services have been started:</span></span>  
  
    -   <span data-ttu-id="33534-175">Служба активации Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="33534-175">Windows Process Activation Service (WAS).</span></span>  
  
    -   <span data-ttu-id="33534-176">Службы IIS: W3SVC.</span><span class="sxs-lookup"><span data-stu-id="33534-176">Internet Information Services (IIS): W3SVC.</span></span>  
  
2.  <span data-ttu-id="33534-177">Затем запустите активатор WasNetActivator.exe.</span><span class="sxs-lookup"><span data-stu-id="33534-177">Then start the activator, WasNetActivator.exe.</span></span> <span data-ttu-id="33534-178">В разделе **активации** вкладка, единственный протокол, **UDP**, выбранного в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="33534-178">Under the **Activation** tab, the only protocol, **UDP**, is selected in the drop down list.</span></span> <span data-ttu-id="33534-179">Нажмите кнопку **запустить** кнопку для запуска активатора.</span><span class="sxs-lookup"><span data-stu-id="33534-179">Click the **Start** button to start the activator.</span></span>  
  
3.  <span data-ttu-id="33534-180">После запуска активатора можно запустить код клиента, запустив файл Client.exe в командном окне.</span><span class="sxs-lookup"><span data-stu-id="33534-180">Once the activator is started, you can run the client code by running Client.exe from a command window.</span></span> <span data-ttu-id="33534-181">Далее приводится образец вывода:</span><span class="sxs-lookup"><span data-stu-id="33534-181">The following is the sample output:</span></span>  
  
    ```  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="33534-182">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="33534-182">The samples may already be installed on your machine.</span></span> <span data-ttu-id="33534-183">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="33534-183">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="33534-184">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33534-184">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="33534-185">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="33534-185">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
  
## <a name="see-also"></a><span data-ttu-id="33534-186">См. также</span><span class="sxs-lookup"><span data-stu-id="33534-186">See Also</span></span>
