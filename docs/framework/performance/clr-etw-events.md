---
title: "События трассировки событий Windows в среде CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: "45"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17701ee1ddbb1056c9b06b2467c4ce10b91271ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clr-etw-events"></a><span data-ttu-id="05ce8-102">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="05ce8-102">CLR ETW Events</span></span>
<span data-ttu-id="05ce8-103">В этом разделе описываются события трассировки событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="05ce8-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="05ce8-104">С каждым событием связаны ключевое слово и уровень, которые описываются в разделе [Ключевые слова и уровни среды CLR (трассировка событий Windows)](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="05ce8-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="05ce8-105">В среде CLR предусмотрены два поставщика событий:</span><span class="sxs-lookup"><span data-stu-id="05ce8-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="05ce8-106">Поставщик среды выполнения вызывает события в зависимости от того, какие ключевые слова (категории событий) активированы.</span><span class="sxs-lookup"><span data-stu-id="05ce8-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="05ce8-107">Поставщик среды выполнения CLR имеет GUID e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="05ce8-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="05ce8-108">Поставщик очистки используется в особых случаях.</span><span class="sxs-lookup"><span data-stu-id="05ce8-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="05ce8-109">Поставщик очистки среды CLR имеет GUID a669021c-c450-4609-a035-5af59af4df18.</span><span class="sxs-lookup"><span data-stu-id="05ce8-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="05ce8-110">Дополнительные сведения см. в разделе [Поставщики трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="05ce8-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05ce8-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="05ce8-111">In This Section</span></span>  
 [<span data-ttu-id="05ce8-112">События сведений времени выполнения</span><span class="sxs-lookup"><span data-stu-id="05ce8-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="05ce8-113">Захватывают информацию о среде выполнения, включая SKU, номер версии, способ активизации среды выполнения, параметры командной строки при ее запуске, GUID (если применимо) и другие релевантные данные.</span><span class="sxs-lookup"><span data-stu-id="05ce8-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="05ce8-114">Событие ExceptionThrown_V1</span><span class="sxs-lookup"><span data-stu-id="05ce8-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="05ce8-115">Захватывает информацию о сгенерированных исключениях.</span><span class="sxs-lookup"><span data-stu-id="05ce8-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="05ce8-116">События конфликтов</span><span class="sxs-lookup"><span data-stu-id="05ce8-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="05ce8-117">Захватывают информацию о конкуренции за блокировки мониторинга или неуправляемые блокировки, используемые исполняющей средой.</span><span class="sxs-lookup"><span data-stu-id="05ce8-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="05ce8-118">События пула потоков</span><span class="sxs-lookup"><span data-stu-id="05ce8-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="05ce8-119">Захватывают информацию о пулах рабочих потоков и пулах потоков ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="05ce8-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="05ce8-120">События загрузчика</span><span class="sxs-lookup"><span data-stu-id="05ce8-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="05ce8-121">Захватывают информацию о загрузке и выгрузке доменов приложения, сборок и модулей.</span><span class="sxs-lookup"><span data-stu-id="05ce8-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="05ce8-122">События методов</span><span class="sxs-lookup"><span data-stu-id="05ce8-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="05ce8-123">Захватывают информацию о методах среды CLR для разрешения символов.</span><span class="sxs-lookup"><span data-stu-id="05ce8-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="05ce8-124">События сборки мусора</span><span class="sxs-lookup"><span data-stu-id="05ce8-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="05ce8-125">Захватывают сведения, относящиеся к сборке мусора, в целях диагностики и отладки.</span><span class="sxs-lookup"><span data-stu-id="05ce8-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="05ce8-126">События трассировки JIT-компилятора</span><span class="sxs-lookup"><span data-stu-id="05ce8-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="05ce8-127">Захватывают информацию о JIT-подстановке (inlining) и концевых вызовах (tail calls).</span><span class="sxs-lookup"><span data-stu-id="05ce8-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="05ce8-128">События взаимодействия</span><span class="sxs-lookup"><span data-stu-id="05ce8-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="05ce8-129">Захватывают информацию о генерации и кэшировании заглушек MSIL.</span><span class="sxs-lookup"><span data-stu-id="05ce8-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="05ce8-130">События ARM</span><span class="sxs-lookup"><span data-stu-id="05ce8-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="05ce8-131">Захватывают детализированную диагностическую информацию о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="05ce8-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="05ce8-132">События безопасности</span><span class="sxs-lookup"><span data-stu-id="05ce8-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="05ce8-133">Захватывают информацию о строгом имени и проверке Authenticode.</span><span class="sxs-lookup"><span data-stu-id="05ce8-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="05ce8-134">События стека</span><span class="sxs-lookup"><span data-stu-id="05ce8-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="05ce8-135">Захватывают информацию, которая используется совместно с другими событиями для генерации трассировок стека после возникновения какого-либо события.</span><span class="sxs-lookup"><span data-stu-id="05ce8-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ce8-136">См. также</span><span class="sxs-lookup"><span data-stu-id="05ce8-136">See Also</span></span>  
 [<span data-ttu-id="05ce8-137">Улучшения отладки и настройки производительности с помощью ETW</span><span class="sxs-lookup"><span data-stu-id="05ce8-137">Improve Debugging And Performance Tuning With ETW</span></span>](http://go.microsoft.com/fwlink/?LinkId=179696)  
 [<span data-ttu-id="05ce8-138">Блог производительности Windows</span><span class="sxs-lookup"><span data-stu-id="05ce8-138">Windows Performance Blog</span></span>](http://go.microsoft.com/fwlink/?LinkId=179509)  
 [<span data-ttu-id="05ce8-139">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="05ce8-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 [<span data-ttu-id="05ce8-140">Поставщики трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="05ce8-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 [<span data-ttu-id="05ce8-141">Ключевые слова и уровни среды CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="05ce8-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 [<span data-ttu-id="05ce8-142">События в среде CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="05ce8-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
