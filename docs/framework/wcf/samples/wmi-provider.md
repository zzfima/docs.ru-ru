---
title: Поставщик WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: dd24a6d270a0bd9012bbda2a53913167c9697bc5
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424511"
---
# <a name="wmi-provider"></a><span data-ttu-id="e5046-102">Поставщик WMI</span><span class="sxs-lookup"><span data-stu-id="e5046-102">WMI Provider</span></span>
<span data-ttu-id="e5046-103">В этом примере показано, как собирать данные из служб Windows Communication Foundation (WCF) во время выполнения с помощью поставщика инструментарий управления Windows (WMI) (WMI), встроенного в WCF.</span><span class="sxs-lookup"><span data-stu-id="e5046-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="e5046-104">Кроме того, в образце показано, как добавлять в службу пользовательский объект инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="e5046-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="e5046-105">В примере активируется поставщик WMI для [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и демонстрируется сбор данных из `ICalculator` службы во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5046-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="e5046-106">Инструментарий WMI - это реализованный корпорацией Майкрософт стандарт управления предприятием через Интернет (WBEM).</span><span class="sxs-lookup"><span data-stu-id="e5046-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="e5046-107">Дополнительные сведения о пакете SDK для инструментария WMI см. в разделе [инструментарий управления Windows (WMI)](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="e5046-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="e5046-108">WBEM является отраслевым стандартом предоставления приложениями инструментария управления для внешних средств управления.</span><span class="sxs-lookup"><span data-stu-id="e5046-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="e5046-109">WCF реализует поставщик WMI, компонент, который предоставляет инструментирование во время выполнения через интерфейс, совместимый с WBEM.</span><span class="sxs-lookup"><span data-stu-id="e5046-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="e5046-110">Средства управления могут подключаться к службам через интерфейс во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5046-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="e5046-111">WCF предоставляет атрибуты служб, такие как адреса, привязки, поведения и прослушиватели.</span><span class="sxs-lookup"><span data-stu-id="e5046-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="e5046-112">Встроенный поставщик инструментария WMI активируется в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e5046-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="e5046-113">Это выполняется с помощью атрибута `wmiProviderEnabled` [диагностики\<](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) в разделе [\<system. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , как показано в следующем образце конфигурации:</span><span class="sxs-lookup"><span data-stu-id="e5046-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="e5046-114">Эта запись конфигурации предоставляет интерфейс инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="e5046-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="e5046-115">Теперь приложения управления могут подключаться через этот интерфейс и обращаться к инструментарию управления приложения.</span><span class="sxs-lookup"><span data-stu-id="e5046-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="e5046-116">Пользовательский объект WMI</span><span class="sxs-lookup"><span data-stu-id="e5046-116">Custom WMI Object</span></span>  
 <span data-ttu-id="e5046-117">Добавление в службу объектов WMI позволяет предоставлять доступ к пользовательским сведениям, а также к сведениям встроенного поставщика WMI.</span><span class="sxs-lookup"><span data-stu-id="e5046-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="e5046-118">Для этого необходимо опубликовать схему службы в инструментарии WMI с помощью приложения Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="e5046-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="e5046-119">Соответствующие инструкции, а также более подробные сведения, см в инструкция по установке в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e5046-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="e5046-120">Доступ к сведениям WMI</span><span class="sxs-lookup"><span data-stu-id="e5046-120">Accessing WMI Information</span></span>  
 <span data-ttu-id="e5046-121">Доступ к данным инструментария WMI может осуществляться несколькими различными способами.</span><span class="sxs-lookup"><span data-stu-id="e5046-121">WMI data can be accessed many different ways.</span></span> <span data-ttu-id="e5046-122">Корпорация Майкрософт предоставляет API-интерфейсы WMI для сценариев, C++ Visual Basic приложений, приложений и .NET Framework (https://docs.microsoft.com/windows/desktop/wmisdk/using-wmi).</span><span class="sxs-lookup"><span data-stu-id="e5046-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework (https://docs.microsoft.com/windows/desktop/wmisdk/using-wmi).</span></span>  
  
 <span data-ttu-id="e5046-123">В этом образце используется два скрипта Java: один - для перечисления выполняющихся на компьютере служб и некоторых их свойств, а второй - для просмотра пользовательских данных инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="e5046-123">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="e5046-124">Скрипт открывает подключение к поставщику инструментария WMI, анализирует данные и отображает собранные данные.</span><span class="sxs-lookup"><span data-stu-id="e5046-124">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="e5046-125">Запустите пример, чтобы создать запущенный экземпляр службы WCF.</span><span class="sxs-lookup"><span data-stu-id="e5046-125">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="e5046-126">Во время работы службы выполните каждый из скриптов Java с помощью следующей команды командной строки:</span><span class="sxs-lookup"><span data-stu-id="e5046-126">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```console  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="e5046-127">Этот скрипт обращается к хранящемуся в службе инструментированию и создает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="e5046-127">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="e5046-128">Затем выполните второй скрипт Java, чтобы отобразить пользовательские данные WMI:</span><span class="sxs-lookup"><span data-stu-id="e5046-128">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="e5046-129">Этот скрипт обращается к хранящемуся в службах пользовательскому инструментированию и создает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="e5046-129">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```console 
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="e5046-130">Сценарий показывает, что на компьютере запущена одна служба.</span><span class="sxs-lookup"><span data-stu-id="e5046-130">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="e5046-131">Служба предоставляет одну конечную точку, реализующую контракт `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="e5046-131">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="e5046-132">Параметры поведения и привязки, реализуемых конечной точкой, задаются в виде отдельных элементов стека обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e5046-132">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="e5046-133">Инструментарий WMI не ограничивается предоставлением инструментария управления инфраструктуры WCF.</span><span class="sxs-lookup"><span data-stu-id="e5046-133">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="e5046-134">Приложение может предоставлять собственные относящиеся к домену элементы данных, используя для этого такой же механизм.</span><span class="sxs-lookup"><span data-stu-id="e5046-134">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="e5046-135">Инструментарий WMI представляет собой единый механизм для контроля веб-службы и управления ею.</span><span class="sxs-lookup"><span data-stu-id="e5046-135">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e5046-136">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e5046-136">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e5046-137">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e5046-137">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e5046-138">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e5046-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e5046-139">Опубликуйте схему служб в WMI, запустив программу InstallUtil.exe (по умолчанию файл InstallUtil.exe расположен в папке «%WINDIR%\Microsoft.NET\Framework\v4.0.30319») для файла service.dll в каталоге размещения.</span><span class="sxs-lookup"><span data-stu-id="e5046-139">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="e5046-140">Эту операцию нужно выполнять только в том случае, если в файл service.dll были внесены изменения.</span><span class="sxs-lookup"><span data-stu-id="e5046-140">This step only needs to be executed when changes have been made to the service.dll file.</span></span>
  
4. <span data-ttu-id="e5046-141">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e5046-141">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e5046-142">Если вы установили WCF после установки ASP.NET, может потребоваться выполнить команду "% WINDIR% \ Microsoft. Net\Framework\v3.0\Windows Communication Фаундатион\сервицемоделрег.ЕКСЕ "-r-x предоставляет учетной записи ASPNET разрешение на публикацию объектов WMI.</span><span class="sxs-lookup"><span data-stu-id="e5046-142">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5. <span data-ttu-id="e5046-143">Для просмотра данных из образцов, доступных через WMI, следует воспользоваться командами: `cscript EnumerateServices.js` или `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="e5046-143">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e5046-144">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e5046-144">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e5046-145">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e5046-145">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="e5046-146">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="e5046-146">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e5046-147">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e5046-147">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="e5046-148">См. также</span><span class="sxs-lookup"><span data-stu-id="e5046-148">See also</span></span>

- [<span data-ttu-id="e5046-149">Примеры мониторинга AppFabric</span><span class="sxs-lookup"><span data-stu-id="e5046-149">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
