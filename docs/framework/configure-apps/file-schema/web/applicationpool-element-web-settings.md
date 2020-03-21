---
title: Элемент <applicationPool> (веб-параметры)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152858"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="54042-102">\<Элемент applicationPool> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="54042-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="54042-103">Отогаляет параметры конфигурации, которые используются ASP.NET для управления поведением в масштабах всего процесса, когда ASP.NET приложение работает в интегрированном режиме на IIS 7.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="54042-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="54042-104">Этот элемент и функция, которую он поддерживает, работают только в том случае, если ваше ASP.NET приложение размещается на IIS 7.0 или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="54042-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="54042-105">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="54042-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="54042-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="54042-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="54042-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span><span class="sxs-lookup"><span data-stu-id="54042-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54042-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54042-108">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54042-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="54042-109">Attributes and Elements</span></span>  

<span data-ttu-id="54042-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="54042-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54042-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="54042-111">Attributes</span></span>  
  
|<span data-ttu-id="54042-112">attribute</span><span class="sxs-lookup"><span data-stu-id="54042-112">Attribute</span></span>|<span data-ttu-id="54042-113">Описание</span><span class="sxs-lookup"><span data-stu-id="54042-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="54042-114">Определяет, сколько одновременных запросов ASP.NET позволяет на процессор.</span><span class="sxs-lookup"><span data-stu-id="54042-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="54042-115">Определяет, сколько одновременных потоков может быть запущено для пула приложений для каждого процессора.</span><span class="sxs-lookup"><span data-stu-id="54042-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="54042-116">Это обеспечивает альтернативный способ управления ASP.NET параллелизма, поскольку можно ограничить количество управляемых потоков, которые могут быть использованы на процессоре для обслуживания запросов.</span><span class="sxs-lookup"><span data-stu-id="54042-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="54042-117">По умолчанию эта настройка составляет 0, что означает, что ASP.NET не ограничивает количество потоков, которые могут быть созданы на процессор, хотя пул потоков CLR также ограничивает количество потоков, которые могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="54042-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="54042-118">Упоняет максимальное количество запросов, которые могут быть в очереди для ASP.NET в одном процессе.</span><span class="sxs-lookup"><span data-stu-id="54042-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="54042-119">Когда два или более ASP.NET приложений работают в одном пуле приложений, совокупный набор запросов, поданных в любое приложение в пуле приложений, подлежит этой настройке.</span><span class="sxs-lookup"><span data-stu-id="54042-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54042-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="54042-120">Child Elements</span></span>  
 <span data-ttu-id="54042-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="54042-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54042-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="54042-122">Parent Elements</span></span>  
  
|<span data-ttu-id="54042-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="54042-123">Element</span></span>|<span data-ttu-id="54042-124">Описание</span><span class="sxs-lookup"><span data-stu-id="54042-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54042-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="54042-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="54042-126">Содержит информацию о том, как ASP.NET взаимодействует с хост-приложением.</span><span class="sxs-lookup"><span data-stu-id="54042-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54042-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="54042-127">Remarks</span></span>  

<span data-ttu-id="54042-128">При запуске IIS 7.0 или более поздней версии в интегрированном режиме эта комбинация элементов позволяет настроить, как ASP.NET управляет потоками и очередями запросов при размещении приложения в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="54042-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="54042-129">Если вы запустите IIS 6 или вы работаете IIS 7.0 в классическом режиме или в режиме ISAPI, эти параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="54042-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="54042-130">Настройки `applicationPool` применяются ко всем пулам приложений, которые работают на определенной версии рамочного соглашения .NET.</span><span class="sxs-lookup"><span data-stu-id="54042-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="54042-131">Настройки содержатся в файле aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="54042-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="54042-132">Существует версия этого файла для версий 2.0 и 4.0 из .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="54042-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="54042-133">(Версии 3.0 и 3.5 рамочного соглашения .NET делятся файлом aspnet.config с версией 2.0.)</span><span class="sxs-lookup"><span data-stu-id="54042-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="54042-134">Если вы работаете IIS 7.0 на Windows 7, вы можете настроить отдельный файл aspnet.config для каждого пула приложений.</span><span class="sxs-lookup"><span data-stu-id="54042-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="54042-135">Это позволяет адаптировать производительность потоков для каждого пула приложений.</span><span class="sxs-lookup"><span data-stu-id="54042-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="54042-136">Для `maxConcurrentRequestsPerCPU` настройки настройки "5000" по умолчанию в рамках .NET 4 эффективно выключает регулирование запроса, которое контролируется ASP.NET, если только у вас на самом деле нет 5000 или более запросов на процессор.</span><span class="sxs-lookup"><span data-stu-id="54042-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="54042-137">Вместо этого параметр по умолчанию зависит от пула потоков CLR для автоматического управления параллелизмом на процессоре.</span><span class="sxs-lookup"><span data-stu-id="54042-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="54042-138">Приложения, широко используют асинхронную обработку запросов или которые имеют много долгосрочных запросов, заблокированных в ввод-во-от сети, выиграют от увеличения лимита по умолчанию в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="54042-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="54042-139">Установка `maxConcurrentRequestsPerCPU` к нулю отключает использование управляемых потоков для обработки ASP.NET запросов.</span><span class="sxs-lookup"><span data-stu-id="54042-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="54042-140">При запуске приложения в пуле приложений IIS запросы остаются на потоке IIS IIS IIS I/O, и поэтому параллелизм регулируется настройками потока IIS.</span><span class="sxs-lookup"><span data-stu-id="54042-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="54042-141">Настройка `requestQueueLimit` работает так же, как `requestQueueLimit` атрибут элемента [processModel,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) который устанавливается в файлах Web.config для ASP.NET приложений.</span><span class="sxs-lookup"><span data-stu-id="54042-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="54042-142">Однако `requestQueueLimit` настройка в файле aspnet.config переопределяет настройки `requestQueueLimit` в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="54042-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="54042-143">Другими словами, если оба атрибута установлены (по `requestQueueLimit` умолчанию это верно), то параметр в файле aspnet.config имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="54042-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54042-144">Пример</span><span class="sxs-lookup"><span data-stu-id="54042-144">Example</span></span>  

<span data-ttu-id="54042-145">В следующем примере показано, как настроить поведение ASP.NET процесса в файле aspnet.config в следующих обстоятельствах:</span><span class="sxs-lookup"><span data-stu-id="54042-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="54042-146">Приложение размещается в пуле приложений IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="54042-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="54042-147">IIS 7.0 работает в интегрированном режиме.</span><span class="sxs-lookup"><span data-stu-id="54042-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="54042-148">Приложение использует .NET Framework 3.5 SP1 или более позднюю версию.</span><span class="sxs-lookup"><span data-stu-id="54042-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="54042-149">Значения в примере являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54042-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="54042-150">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="54042-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54042-151">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="54042-151">Namespace</span></span>||  
|<span data-ttu-id="54042-152">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="54042-152">Schema Name</span></span>||  
|<span data-ttu-id="54042-153">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="54042-153">Validation File</span></span>||  
|<span data-ttu-id="54042-154">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="54042-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="54042-155">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="54042-155">See also</span></span>

- [<span data-ttu-id="54042-156">\<system.web> элемент (веб-настройки)</span><span class="sxs-lookup"><span data-stu-id="54042-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
