---
title: События трассировки событий Windows в среде CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
ms.openlocfilehash: e879dcf385acbc522c0a3573cfa374550ea23333
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504123"
---
# <a name="clr-etw-events"></a><span data-ttu-id="8b9df-102">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="8b9df-102">CLR ETW Events</span></span>
<span data-ttu-id="8b9df-103">В этом разделе описываются события трассировки событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="8b9df-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="8b9df-104">С каждым событием связаны ключевое слово и уровень, которые описываются в разделе [Ключевые слова и уровни среды CLR (трассировка событий Windows)](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8b9df-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="8b9df-105">В среде CLR предусмотрены два поставщика событий:</span><span class="sxs-lookup"><span data-stu-id="8b9df-105">The CLR has two providers for the events:</span></span>  
  
- <span data-ttu-id="8b9df-106">Поставщик среды выполнения вызывает события в зависимости от того, какие ключевые слова (категории событий) активированы.</span><span class="sxs-lookup"><span data-stu-id="8b9df-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="8b9df-107">Поставщик среды выполнения CLR имеет GUID e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="8b9df-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
- <span data-ttu-id="8b9df-108">Поставщик очистки используется в особых случаях.</span><span class="sxs-lookup"><span data-stu-id="8b9df-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="8b9df-109">Поставщик очистки среды CLR имеет GUID a669021c-c450-4609-a035-5af59af4df18.</span><span class="sxs-lookup"><span data-stu-id="8b9df-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="8b9df-110">Дополнительные сведения см. в разделе [Поставщики трассировки событий Windows в среде CLR](clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="8b9df-110">For more information about the providers, see [CLR ETW Providers](clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b9df-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8b9df-111">In This Section</span></span>  
 [<span data-ttu-id="8b9df-112">События сведений времени выполнения</span><span class="sxs-lookup"><span data-stu-id="8b9df-112">Runtime Information Events</span></span>](runtime-information-etw-events.md)  
 <span data-ttu-id="8b9df-113">Захватывают информацию о среде выполнения, включая SKU, номер версии, способ активизации среды выполнения, параметры командной строки при ее запуске, GUID (если применимо) и другие релевантные данные.</span><span class="sxs-lookup"><span data-stu-id="8b9df-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="8b9df-114">Событие ExceptionThrown_V1</span><span class="sxs-lookup"><span data-stu-id="8b9df-114">Exception Thrown_V1 Event</span></span>](exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="8b9df-115">Захватывает информацию о сгенерированных исключениях.</span><span class="sxs-lookup"><span data-stu-id="8b9df-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="8b9df-116">События конфликтов</span><span class="sxs-lookup"><span data-stu-id="8b9df-116">Contention Events</span></span>](contention-etw-events.md)  
 <span data-ttu-id="8b9df-117">Захватывают информацию о конкуренции за блокировки мониторинга или неуправляемые блокировки, используемые исполняющей средой.</span><span class="sxs-lookup"><span data-stu-id="8b9df-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="8b9df-118">События пула потоков</span><span class="sxs-lookup"><span data-stu-id="8b9df-118">Thread Pool Events</span></span>](thread-pool-etw-events.md)  
 <span data-ttu-id="8b9df-119">Захватывают информацию о пулах рабочих потоков и пулах потоков ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="8b9df-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="8b9df-120">События загрузчика</span><span class="sxs-lookup"><span data-stu-id="8b9df-120">Loader Events</span></span>](loader-etw-events.md)  
 <span data-ttu-id="8b9df-121">Захватывают информацию о загрузке и выгрузке доменов приложения, сборок и модулей.</span><span class="sxs-lookup"><span data-stu-id="8b9df-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="8b9df-122">События методов</span><span class="sxs-lookup"><span data-stu-id="8b9df-122">Method Events</span></span>](method-etw-events.md)  
 <span data-ttu-id="8b9df-123">Захватывают информацию о методах среды CLR для разрешения символов.</span><span class="sxs-lookup"><span data-stu-id="8b9df-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="8b9df-124">События сборки мусора</span><span class="sxs-lookup"><span data-stu-id="8b9df-124">Garbage Collection Events</span></span>](garbage-collection-etw-events.md)  
 <span data-ttu-id="8b9df-125">Захватывают сведения, относящиеся к сборке мусора, в целях диагностики и отладки.</span><span class="sxs-lookup"><span data-stu-id="8b9df-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="8b9df-126">События трассировки JIT-компилятора</span><span class="sxs-lookup"><span data-stu-id="8b9df-126">JIT Tracing Events</span></span>](jit-tracing-etw-events.md)  
 <span data-ttu-id="8b9df-127">Захватывают информацию о JIT-подстановке (inlining) и концевых вызовах (tail calls).</span><span class="sxs-lookup"><span data-stu-id="8b9df-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="8b9df-128">События взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8b9df-128">Interop Events</span></span>](interop-etw-events.md)  
 <span data-ttu-id="8b9df-129">Захватывают информацию о генерации и кэшировании заглушек MSIL.</span><span class="sxs-lookup"><span data-stu-id="8b9df-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="8b9df-130">События ARM</span><span class="sxs-lookup"><span data-stu-id="8b9df-130">ARM Events</span></span>](application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="8b9df-131">Захватывают детализированную диагностическую информацию о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8b9df-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="8b9df-132">События безопасности</span><span class="sxs-lookup"><span data-stu-id="8b9df-132">Security Events</span></span>](security-etw-events.md)  
 <span data-ttu-id="8b9df-133">Захватывают информацию о строгом имени и проверке Authenticode.</span><span class="sxs-lookup"><span data-stu-id="8b9df-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="8b9df-134">События стека</span><span class="sxs-lookup"><span data-stu-id="8b9df-134">Stack Event</span></span>](stack-etw-event.md)  
 <span data-ttu-id="8b9df-135">Захватывают информацию, которая используется совместно с другими событиями для генерации трассировок стека после возникновения какого-либо события.</span><span class="sxs-lookup"><span data-stu-id="8b9df-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9df-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="8b9df-136">See also</span></span>

- [<span data-ttu-id="8b9df-137">Усовершенствованные отладка и настройка производительности с помощью приложения ETW</span><span class="sxs-lookup"><span data-stu-id="8b9df-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)
- [<span data-ttu-id="8b9df-138">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b9df-138">Controlling .NET Framework Logging</span></span>](controlling-logging.md)
- [<span data-ttu-id="8b9df-139">Поставщики трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="8b9df-139">CLR ETW Providers</span></span>](clr-etw-providers.md)
- [<span data-ttu-id="8b9df-140">Ключевые слова и уровни среды CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="8b9df-140">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="8b9df-141">События в среде CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="8b9df-141">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
