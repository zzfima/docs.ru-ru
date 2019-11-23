---
title: Счетчики производительности WCF
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: 73bb02379308fbfe507137e61ac8d84e6b9760b4
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395902"
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="0ced2-102">Счетчики производительности WCF</span><span class="sxs-lookup"><span data-stu-id="0ced2-102">WCF Performance Counters</span></span>
<span data-ttu-id="0ced2-103">Windows Communication Foundation (WCF) включает большой набор счетчиков производительности, помогающих оценить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="0ced2-103">Windows Communication Foundation (WCF) includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="0ced2-104">Включение счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="0ced2-104">Enabling Performance Counters</span></span>  
 <span data-ttu-id="0ced2-105">Вы можете включить счетчики производительности для службы WCF с помощью файла конфигурации App. config службы WCF, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="0ced2-105">You can enable performance counters for a WCF service through the app.config configuration file of the WCF service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="0ced2-106">Атрибут `performanceCounters` можно настроить так, чтобы включать определенный тип счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="0ced2-106">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="0ced2-107">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0ced2-107">Valid values are</span></span>  
  
- <span data-ttu-id="0ced2-108">All. Включены счетчики всех категорий (ServiceModelService, ServiceModelEndpoint и ServiceModelOperation).</span><span class="sxs-lookup"><span data-stu-id="0ced2-108">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
- <span data-ttu-id="0ced2-109">ServiceOnly. Включены только счетчики категории ServiceModelService.</span><span class="sxs-lookup"><span data-stu-id="0ced2-109">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="0ced2-110">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0ced2-110">This is the default value.</span></span>  
  
- <span data-ttu-id="0ced2-111">Off. Счетчики производительности ServiceModel\* отключены.</span><span class="sxs-lookup"><span data-stu-id="0ced2-111">Off: ServiceModel\* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="0ced2-112">Если вы хотите включить счетчики производительности для всех приложений WCF, можно поместить параметры конфигурации в файл Machine. config.</span><span class="sxs-lookup"><span data-stu-id="0ced2-112">If you want to enable performance counters for all WCF applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="0ced2-113">Дополнительные сведения о настройке достаточного объема памяти для счетчиков производительности на компьютере см. в разделе **увеличение объема памяти для счетчиков производительности** .</span><span class="sxs-lookup"><span data-stu-id="0ced2-113">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="0ced2-114">При использовании точек расширения WCF, таких как пользовательские вызывающие операции, следует также создавать собственные счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="0ced2-114">If you use WCF extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="0ced2-115">Это связано с тем, что при реализации точки расширения WCF может больше не создавать стандартные данные счетчиков производительности в пути по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0ced2-115">This is because if you implement an extensibility point, WCF may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="0ced2-116">Если поддержка трассировки вручную путем создания счетчика производительности не реализована, можно не увидеть ожидаемые данные счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="0ced2-116">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="0ced2-117">Также счетчики производительности можно включить в коде следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0ced2-117">You can also enable performance counters in your code as follows,</span></span>  
  
```csharp
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a><span data-ttu-id="0ced2-118">Просмотр данных производительности</span><span class="sxs-lookup"><span data-stu-id="0ced2-118">Viewing Performance Data</span></span>  
 <span data-ttu-id="0ced2-119">Чтобы просмотреть данные, полученные от счетчиков производительности, можно использовать системный монитор (Perfmon.exe), поставляемый вместе с Windows.</span><span class="sxs-lookup"><span data-stu-id="0ced2-119">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="0ced2-120">Это средство можно запустить, перейдя в меню **Пуск**, выбрав пункт **выполнить** и наберите `perfmon.exe` в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="0ced2-120">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ced2-121">Экземпляры счетчиков производительности могут быть выпущены до того, как диспетчер конечной точки обработает последние сообщения.</span><span class="sxs-lookup"><span data-stu-id="0ced2-121">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="0ced2-122">Это может привести к тому, что данные производительности для некоторых сообщений не будут получены.</span><span class="sxs-lookup"><span data-stu-id="0ced2-122">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="0ced2-123">Увеличение объема памяти для счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="0ced2-123">Increasing Memory Size for Performance Counters</span></span>  
 <span data-ttu-id="0ced2-124">WCF использует отдельную общую память для категорий счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="0ced2-124">WCF uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="0ced2-125">По умолчанию объем отдельной общей памяти составляет четвертую часть от объема глобальной памяти счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="0ced2-125">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="0ced2-126">По умолчанию объем глобальной памяти счетчиков производительности составляет 524 288 байт.</span><span class="sxs-lookup"><span data-stu-id="0ced2-126">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="0ced2-127">Таким образом, три категории счетчиков производительности WCF по умолчанию имеют размер около 128 КБ.</span><span class="sxs-lookup"><span data-stu-id="0ced2-127">Therefore, the three WCF performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="0ced2-128">В зависимости от характеристик среды выполнения приложений WCF на компьютере память счетчика производительности может быть исчерпана.</span><span class="sxs-lookup"><span data-stu-id="0ced2-128">Depending upon the runtime characteristics of the WCF applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="0ced2-129">В этом случае WCF записывает ошибку в журнал событий приложений.</span><span class="sxs-lookup"><span data-stu-id="0ced2-129">When this happens, WCF writes an error to the application event log.</span></span> <span data-ttu-id="0ced2-130">В содержимом ошибки указывается, что счетчик производительности не был загружен, и запись содержит исключение "System.InvalidOperationException: не хватает памяти для просмотра файла пользовательских счетчиков".</span><span class="sxs-lookup"><span data-stu-id="0ced2-130">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="0ced2-131">Если включена трассировка на уровне ошибок, этот сбой также трассируется.</span><span class="sxs-lookup"><span data-stu-id="0ced2-131">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="0ced2-132">Если память счетчика производительности исчерпана, продолжение выполнения приложений WCF с включенными счетчиками производительности может привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="0ced2-132">If performance counter memory is exhausted, continuing to run your WCF applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="0ced2-133">Если вы обладаете правами администратора данного компьютера, настройте его так, чтобы выделить достаточно памяти для поддержки максимального количества счетчиков производительности, которые могут существовать в любое время.</span><span class="sxs-lookup"><span data-stu-id="0ced2-133">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="0ced2-134">В реестре можно изменить объем памяти счетчика производительности для категорий WCF.</span><span class="sxs-lookup"><span data-stu-id="0ced2-134">You can change the amount of performance counter memory for WCF categories in the registry.</span></span> <span data-ttu-id="0ced2-135">Для этого необходимо добавить новое значение DWORD с именем `FileMappingSize` в три следующих расположения и задать для него требуемое значение в байтах.</span><span class="sxs-lookup"><span data-stu-id="0ced2-135">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="0ced2-136">Перезагрузите компьютер, чтобы эти изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="0ced2-136">Reboot your machine so that these changes are taken into effect.</span></span>  
  
- <span data-ttu-id="0ced2-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="0ced2-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
- <span data-ttu-id="0ced2-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="0ced2-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
- <span data-ttu-id="0ced2-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="0ced2-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="0ced2-140">Если множество объектов (например, ServiceHost) удаляется, но ожидает сборки мусора, счетчик производительности `PrivateBytes` регистрирует необычно большое количество объектов.</span><span class="sxs-lookup"><span data-stu-id="0ced2-140">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="0ced2-141">Чтобы устранить эту проблему, можно либо добавить собственные счетчики, относящиеся к приложению, либо использовать атрибут `performanceCounters`, чтобы включить только счетчики уровня службы.</span><span class="sxs-lookup"><span data-stu-id="0ced2-141">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="0ced2-142">Типы счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="0ced2-142">Types of Performance Counters</span></span>  
 <span data-ttu-id="0ced2-143">Счетчики производительности группируются по трем различным уровням: служба, конечная точка и операция.</span><span class="sxs-lookup"><span data-stu-id="0ced2-143">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="0ced2-144">Можно использовать инструментарий WMI, чтобы получить имя экземпляра счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="0ced2-144">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="0ced2-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="0ced2-145">For example,</span></span>  
  
- <span data-ttu-id="0ced2-146">Имя экземпляра счетчика службы можно получить с помощью свойства "Каунтеринстанценаме" экземпляра [службы](../wmi/service.md) WMI.</span><span class="sxs-lookup"><span data-stu-id="0ced2-146">Service counter instance name can be obtained through WMI [Service](../wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
- <span data-ttu-id="0ced2-147">Имя экземпляра счетчика конечной точки можно получить с помощью свойства "Каунтеринстанценаме" экземпляра [конечной точки](../wmi/endpoint.md) WMI.</span><span class="sxs-lookup"><span data-stu-id="0ced2-147">Endpoint counter instance name can be obtained through WMI [Endpoint](../wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
- <span data-ttu-id="0ced2-148">Имя экземпляра счетчика операции можно получить с помощью метода "Жетоператионкаунтеринстанценаме" экземпляра [конечной точки](../wmi/endpoint.md) WMI.</span><span class="sxs-lookup"><span data-stu-id="0ced2-148">Operation counter instance name can be obtained through WMI [Endpoint](../wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="0ced2-149">Дополнительные сведения об инструментарии WMI см. в разделе [использование инструментарий управления Windows (WMI) для диагностики](../wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ced2-149">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="0ced2-150">Счетчики производительности службы</span><span class="sxs-lookup"><span data-stu-id="0ced2-150">Service performance counters</span></span>  
 <span data-ttu-id="0ced2-151">Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы.</span><span class="sxs-lookup"><span data-stu-id="0ced2-151">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="0ced2-152">Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelService 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="0ced2-152">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="0ced2-153">Экземпляры именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="0ced2-153">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
 <span data-ttu-id="0ced2-154">Счетчик в области действия службы агрегируется из счетчика в коллекции конечных точек.</span><span class="sxs-lookup"><span data-stu-id="0ced2-154">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="0ced2-155">Значение счетчиков производительности для создания экземпляра службы увеличивается при создании нового InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="0ced2-155">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="0ced2-156">Обратите внимание, что новый InstanceContext создается даже при получении неактивирующего сообщения (с существующей службой) или при подключении к экземпляру из одного сеанса, завершении сеанса и последующем повторном подключении из другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="0ced2-156">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="0ced2-157">Счетчики производительности конечных точек</span><span class="sxs-lookup"><span data-stu-id="0ced2-157">Endpoint performance counters</span></span>  
 <span data-ttu-id="0ced2-158">Счетчики производительности конечных точек позволяют просматривать данные о том, как именно конечная точка принимает сообщения.</span><span class="sxs-lookup"><span data-stu-id="0ced2-158">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="0ced2-159">Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelEndpoint 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="0ced2-159">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="0ced2-160">Экземпляры именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="0ced2-160">The instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName)@(endpoint listener address)`
  
 <span data-ttu-id="0ced2-161">Данные аналогичны данным, собираемым для отдельных операций, но агрегируются только на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="0ced2-161">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="0ced2-162">Счетчик в области действия конечной точки агрегируется из счетчиков в коллекции операций.</span><span class="sxs-lookup"><span data-stu-id="0ced2-162">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ced2-163">Если две конечные точки имеют идентичные имена контрактов и адреса, они сопоставляются с одним и тем же экземпляром счетчика.</span><span class="sxs-lookup"><span data-stu-id="0ced2-163">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="0ced2-164">Счетчики производительности операций</span><span class="sxs-lookup"><span data-stu-id="0ced2-164">Operation performance counters</span></span>  
 <span data-ttu-id="0ced2-165">Счетчики производительности операций можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelOperation 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="0ced2-165">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="0ced2-166">Каждая операция содержит отдельный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="0ced2-166">Each operation has an individual instance.</span></span> <span data-ttu-id="0ced2-167">Следовательно, если указанный контракт имеет 10 операций, 10 экземпляров счетчика операций связаны с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="0ced2-167">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="0ced2-168">Экземпляры объекта именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="0ced2-168">The object instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 <span data-ttu-id="0ced2-169">Этот счетчик позволяет измерить, как используется вызов и насколько успешно выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="0ced2-169">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="0ced2-170">Если счетчики видимы в нескольких областях, данные, полученные из более высокой области, агрегируются с данными, полученными из более низких областей.</span><span class="sxs-lookup"><span data-stu-id="0ced2-170">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="0ced2-171">Например, `Calls` в конечной точке представляет сумму всех вызовов операций в конечной точке. `Calls` в службе представляет сумму все вызовов всех конечных точек в службе.</span><span class="sxs-lookup"><span data-stu-id="0ced2-171">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ced2-172">При наличии одинаковых имен операций в контракте можно получить только экземпляры одного счетчика для обоих операций.</span><span class="sxs-lookup"><span data-stu-id="0ced2-172">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="0ced2-173">Программирование счетчиков производительности WCF</span><span class="sxs-lookup"><span data-stu-id="0ced2-173">Programming the WCF Performance Counters</span></span>  

<span data-ttu-id="0ced2-174">Несколько файлов устанавливаются в папку установки пакета SDK, что позволяет программно получить доступ к счетчикам производительности WCF.</span><span class="sxs-lookup"><span data-stu-id="0ced2-174">Several files are installed in the SDK install folder so that you can access the WCF performance counters programmatically.</span></span> <span data-ttu-id="0ced2-175">Эти файлы перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="0ced2-175">These files are listed as follows:</span></span>
  
- <span data-ttu-id="0ced2-176">*\_Сервицемоделендпоинтперфкаунтерс. ВРГ*</span><span class="sxs-lookup"><span data-stu-id="0ced2-176">*\_ServiceModelEndpointPerfCounters.vrg*</span></span>
- <span data-ttu-id="0ced2-177">*\_Сервицемоделоператионперфкаунтерс. ВРГ*</span><span class="sxs-lookup"><span data-stu-id="0ced2-177">*\_ServiceModelOperationPerfCounters.vrg*</span></span>
- <span data-ttu-id="0ced2-178">*\_Сервицемоделсервицеперфкаунтерс. ВРГ*</span><span class="sxs-lookup"><span data-stu-id="0ced2-178">*\_ServiceModelServicePerfCounters.vrg*</span></span>  
- <span data-ttu-id="0ced2-179">*\_Смсвчостперфкаунтерс. ВРГ*</span><span class="sxs-lookup"><span data-stu-id="0ced2-179">*\_SMSvcHostPerfCounters.vrg*</span></span>
- <span data-ttu-id="0ced2-180">*\_Трансактионбриджеперфкаунтерс. ВРГ*</span><span class="sxs-lookup"><span data-stu-id="0ced2-180">*\_TransactionBridgePerfCounters.vrg*</span></span>
  
<span data-ttu-id="0ced2-181">Дополнительные сведения о программном доступе к счетчикам см. в разделе [Архитектура программирования счетчика производительности](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/5f9bkxzf(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0ced2-181">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/5f9bkxzf(v=vs.90)).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ced2-182">См. также:</span><span class="sxs-lookup"><span data-stu-id="0ced2-182">See also</span></span>

- [<span data-ttu-id="0ced2-183">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="0ced2-183">Administration and Diagnostics</span></span>](../index.md)
