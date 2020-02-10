---
title: Поставщик WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: a170a20212791d789af589c1ff99dcd1abad1c9e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094778"
---
# <a name="wmi-provider"></a><span data-ttu-id="d06f7-102">Поставщик WMI</span><span class="sxs-lookup"><span data-stu-id="d06f7-102">WMI Provider</span></span>
<span data-ttu-id="d06f7-103">В этом примере показано, как собирать данные из служб Windows Communication Foundation (WCF) во время выполнения с помощью поставщика инструментарий управления Windows (WMI) (WMI), встроенного в WCF.</span><span class="sxs-lookup"><span data-stu-id="d06f7-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="d06f7-104">Кроме того, в образце показано, как добавлять в службу пользовательский объект инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="d06f7-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="d06f7-105">В примере активируется поставщик WMI для [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и демонстрируется сбор данных из `ICalculator` службы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d06f7-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="d06f7-106">Инструментарий WMI - это реализованный корпорацией Майкрософт стандарт управления предприятием через Интернет (WBEM).</span><span class="sxs-lookup"><span data-stu-id="d06f7-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="d06f7-107">Дополнительные сведения о пакете SDK для инструментария WMI см. в разделе [инструментарий управления Windows (WMI)](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="d06f7-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="d06f7-108">WBEM является отраслевым стандартом предоставления приложениями инструментария управления для внешних средств управления.</span><span class="sxs-lookup"><span data-stu-id="d06f7-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="d06f7-109">WCF реализует поставщик WMI, компонент, который предоставляет инструментирование во время выполнения через интерфейс, совместимый с WBEM.</span><span class="sxs-lookup"><span data-stu-id="d06f7-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="d06f7-110">Средства управления могут подключаться к службам через интерфейс во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d06f7-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="d06f7-111">WCF предоставляет атрибуты служб, такие как адреса, привязки, поведения и прослушиватели.</span><span class="sxs-lookup"><span data-stu-id="d06f7-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="d06f7-112">Встроенный поставщик инструментария WMI активируется в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d06f7-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="d06f7-113">Это выполняется с помощью атрибута `wmiProviderEnabled` [диагностики\<>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) в разделе [\<system. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , как показано в следующем образце конфигурации:</span><span class="sxs-lookup"><span data-stu-id="d06f7-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="d06f7-114">Эта запись конфигурации предоставляет интерфейс инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="d06f7-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="d06f7-115">Теперь приложения управления могут подключаться через этот интерфейс и обращаться к инструментарию управления приложения.</span><span class="sxs-lookup"><span data-stu-id="d06f7-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="d06f7-116">Пользовательский объект WMI</span><span class="sxs-lookup"><span data-stu-id="d06f7-116">Custom WMI Object</span></span>  
 <span data-ttu-id="d06f7-117">Добавление в службу объектов WMI позволяет предоставлять доступ к пользовательским сведениям, а также к сведениям встроенного поставщика WMI.</span><span class="sxs-lookup"><span data-stu-id="d06f7-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="d06f7-118">Для этого необходимо опубликовать схему службы в инструментарии WMI с помощью приложения Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="d06f7-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="d06f7-119">Соответствующие инструкции, а также более подробные сведения, см в инструкция по установке в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="d06f7-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="d06f7-120">Доступ к сведениям WMI</span><span class="sxs-lookup"><span data-stu-id="d06f7-120">Accessing WMI Information</span></span>  

<span data-ttu-id="d06f7-121">Доступ к данным инструментария WMI может осуществляться несколькими различными способами.</span><span class="sxs-lookup"><span data-stu-id="d06f7-121">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="d06f7-122">Корпорация Майкрософт предоставляет API-интерфейсы WMI для сценариев, C++ Visual Basic приложений, приложений и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d06f7-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework.</span></span> <span data-ttu-id="d06f7-123">Дополнительные сведения см. [в разделе Использование WMI](/windows/desktop/wmisdk/using-wmi).</span><span class="sxs-lookup"><span data-stu-id="d06f7-123">For more information, see [Using WMI](/windows/desktop/wmisdk/using-wmi).</span></span>
  
 <span data-ttu-id="d06f7-124">В этом образце используется два скрипта Java: один - для перечисления выполняющихся на компьютере служб и некоторых их свойств, а второй - для просмотра пользовательских данных инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="d06f7-124">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="d06f7-125">Скрипт открывает подключение к поставщику инструментария WMI, анализирует данные и отображает собранные данные.</span><span class="sxs-lookup"><span data-stu-id="d06f7-125">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="d06f7-126">Запустите пример, чтобы создать запущенный экземпляр службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d06f7-126">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="d06f7-127">Во время работы службы выполните каждый из скриптов Java с помощью следующей команды командной строки:</span><span class="sxs-lookup"><span data-stu-id="d06f7-127">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```console  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="d06f7-128">Этот скрипт обращается к хранящемуся в службе инструментированию и создает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="d06f7-128">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```console  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 <span data-ttu-id="d06f7-129">Затем выполните второй скрипт Java, чтобы отобразить пользовательские данные WMI:</span><span class="sxs-lookup"><span data-stu-id="d06f7-129">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="d06f7-130">Этот скрипт обращается к хранящемуся в службах пользовательскому инструментированию и создает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="d06f7-130">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```console 
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="d06f7-131">Сценарий показывает, что на компьютере запущена одна служба.</span><span class="sxs-lookup"><span data-stu-id="d06f7-131">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="d06f7-132">Служба предоставляет одну конечную точку, реализующую контракт `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="d06f7-132">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="d06f7-133">Параметры поведения и привязки, реализуемых конечной точкой, задаются в виде отдельных элементов стека обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d06f7-133">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="d06f7-134">Инструментарий WMI не ограничивается предоставлением инструментария управления инфраструктуры WCF.</span><span class="sxs-lookup"><span data-stu-id="d06f7-134">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="d06f7-135">Приложение может предоставлять собственные относящиеся к домену элементы данных, используя для этого такой же механизм.</span><span class="sxs-lookup"><span data-stu-id="d06f7-135">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="d06f7-136">Инструментарий WMI представляет собой единый механизм для контроля веб-службы и управления ею.</span><span class="sxs-lookup"><span data-stu-id="d06f7-136">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d06f7-137">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d06f7-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d06f7-138">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d06f7-138">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d06f7-139">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d06f7-139">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="d06f7-140">Опубликуйте схему служб в WMI, запустив программу InstallUtil.exe (по умолчанию файл InstallUtil.exe расположен в папке «%WINDIR%\Microsoft.NET\Framework\v4.0.30319») для файла service.dll в каталоге размещения.</span><span class="sxs-lookup"><span data-stu-id="d06f7-140">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="d06f7-141">Эту операцию нужно выполнять только в том случае, если в файл service.dll были внесены изменения.</span><span class="sxs-lookup"><span data-stu-id="d06f7-141">This step only needs to be executed when changes have been made to the service.dll file.</span></span>
  
4. <span data-ttu-id="d06f7-142">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d06f7-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d06f7-143">Если вы установили WCF после установки ASP.NET, может потребоваться выполнить команду "% WINDIR% \ Microsoft. Net\Framework\v3.0\Windows Communication Фаундатион\сервицемоделрег.ЕКСЕ "-r-x предоставляет учетной записи ASPNET разрешение на публикацию объектов WMI.</span><span class="sxs-lookup"><span data-stu-id="d06f7-143">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5. <span data-ttu-id="d06f7-144">Для просмотра данных из образцов, доступных через WMI, следует воспользоваться командами: `cscript EnumerateServices.js` или `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="d06f7-144">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d06f7-145">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d06f7-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d06f7-146">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d06f7-146">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="d06f7-147">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="d06f7-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d06f7-148">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d06f7-148">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="d06f7-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d06f7-149">See also</span></span>

- <span data-ttu-id="d06f7-150">[Примеры мониторинга AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d06f7-150">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
