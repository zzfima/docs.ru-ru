---
title: "События отслеживания ресурсов домена приложения (трассировка событий Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a93e8cc1ab0b7488f920b556d2073d2813c3b7a9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="a169c-102">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="a169c-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<span data-ttu-id="a169c-103"><a name="top"></a> Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="a169c-103"><a name="top"></a> These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="a169c-104">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="a169c-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="a169c-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="a169c-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a169c-106">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="a169c-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="a169c-107">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="a169c-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="a169c-108">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="a169c-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="a169c-109">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="a169c-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="a169c-110">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="a169c-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="a169c-111">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="a169c-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="a169c-112">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="a169c-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="a169c-113">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="a169c-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="a169c-114">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="a169c-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="a169c-115">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="a169c-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a169c-116">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a169c-116">Keyword for raising the event</span></span>|<span data-ttu-id="a169c-117">Уровень</span><span class="sxs-lookup"><span data-stu-id="a169c-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a169c-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a169c-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a169c-119">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-119">Informational(4)</span></span>|  
|<span data-ttu-id="a169c-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a169c-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a169c-121">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="a169c-122">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a169c-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a169c-123">Событие</span><span class="sxs-lookup"><span data-stu-id="a169c-123">Event</span></span>|<span data-ttu-id="a169c-124">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a169c-124">Event ID</span></span>|<span data-ttu-id="a169c-125">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a169c-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="a169c-126">85</span><span class="sxs-lookup"><span data-stu-id="a169c-126">85</span></span>|<span data-ttu-id="a169c-127">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="a169c-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="a169c-128">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a169c-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a169c-129">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a169c-129">Field name</span></span>|<span data-ttu-id="a169c-130">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a169c-130">Data type</span></span>|<span data-ttu-id="a169c-131">Описание</span><span class="sxs-lookup"><span data-stu-id="a169c-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a169c-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a169c-132">ThreadID</span></span>|<span data-ttu-id="a169c-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-133">win:UInt64</span></span>|<span data-ttu-id="a169c-134">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="a169c-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a169c-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a169c-135">AppDomainID</span></span>|<span data-ttu-id="a169c-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-136">win:UInt64</span></span>|<span data-ttu-id="a169c-137">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="a169c-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="a169c-138">Флаги</span><span class="sxs-lookup"><span data-stu-id="a169c-138">Flags</span></span>|<span data-ttu-id="a169c-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a169c-139">win:UInt32</span></span>|<span data-ttu-id="a169c-140">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="a169c-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="a169c-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="a169c-141">ManagedThreadIndex</span></span>|<span data-ttu-id="a169c-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a169c-142">win:UInt32</span></span>|<span data-ttu-id="a169c-143">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="a169c-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="a169c-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="a169c-144">OSThreadID</span></span>|<span data-ttu-id="a169c-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a169c-145">win:UInt32</span></span>|<span data-ttu-id="a169c-146">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="a169c-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="a169c-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a169c-147">ClrInstanceID</span></span>|<span data-ttu-id="a169c-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a169c-148">win:UInt16</span></span>|<span data-ttu-id="a169c-149">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a169c-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a169c-150">К началу</span><span class="sxs-lookup"><span data-stu-id="a169c-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="a169c-151">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="a169c-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="a169c-152">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="a169c-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a169c-153">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a169c-153">Keyword for raising the event</span></span>|<span data-ttu-id="a169c-154">Уровень</span><span class="sxs-lookup"><span data-stu-id="a169c-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a169c-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a169c-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a169c-156">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="a169c-157">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a169c-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a169c-158">Событие</span><span class="sxs-lookup"><span data-stu-id="a169c-158">Event</span></span>|<span data-ttu-id="a169c-159">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a169c-159">Event ID</span></span>|<span data-ttu-id="a169c-160">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a169c-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="a169c-161">83</span><span class="sxs-lookup"><span data-stu-id="a169c-161">83</span></span>|<span data-ttu-id="a169c-162">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="a169c-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="a169c-163">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a169c-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a169c-164">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a169c-164">Field name</span></span>|<span data-ttu-id="a169c-165">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a169c-165">Data type</span></span>|<span data-ttu-id="a169c-166">Описание</span><span class="sxs-lookup"><span data-stu-id="a169c-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a169c-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a169c-167">AppDomainID</span></span>|<span data-ttu-id="a169c-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-168">win:UInt64</span></span>|<span data-ttu-id="a169c-169">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a169c-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a169c-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="a169c-170">Allocated</span></span>|<span data-ttu-id="a169c-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-171">win:UInt64</span></span>|<span data-ttu-id="a169c-172">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="a169c-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="a169c-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a169c-173">ClrInstanceID</span></span>|<span data-ttu-id="a169c-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a169c-174">win:UInt16</span></span>|<span data-ttu-id="a169c-175">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a169c-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a169c-176">К началу</span><span class="sxs-lookup"><span data-stu-id="a169c-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="a169c-177">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="a169c-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="a169c-178">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="a169c-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a169c-179">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a169c-179">Keyword for raising the event</span></span>|<span data-ttu-id="a169c-180">Уровень</span><span class="sxs-lookup"><span data-stu-id="a169c-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a169c-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a169c-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a169c-182">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="a169c-183">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a169c-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a169c-184">Событие</span><span class="sxs-lookup"><span data-stu-id="a169c-184">Event</span></span>|<span data-ttu-id="a169c-185">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a169c-185">Event ID</span></span>|<span data-ttu-id="a169c-186">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a169c-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="a169c-187">84</span><span class="sxs-lookup"><span data-stu-id="a169c-187">84</span></span>|<span data-ttu-id="a169c-188">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="a169c-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="a169c-189">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a169c-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a169c-190">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a169c-190">Field name</span></span>|<span data-ttu-id="a169c-191">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a169c-191">Data type</span></span>|<span data-ttu-id="a169c-192">Описание</span><span class="sxs-lookup"><span data-stu-id="a169c-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a169c-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a169c-193">AppDomainID</span></span>|<span data-ttu-id="a169c-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-194">win:UInt64</span></span>|<span data-ttu-id="a169c-195">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a169c-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="a169c-196">Survived</span><span class="sxs-lookup"><span data-stu-id="a169c-196">Survived</span></span>|<span data-ttu-id="a169c-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-197">win:UInt64</span></span>|<span data-ttu-id="a169c-198">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="a169c-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="a169c-199">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="a169c-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="a169c-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="a169c-200">ProcessSurvived</span></span>|<span data-ttu-id="a169c-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-201">win:UInt64</span></span>|<span data-ttu-id="a169c-202">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a169c-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="a169c-203">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="a169c-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="a169c-204">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="a169c-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="a169c-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a169c-205">ClrInstanceID</span></span>|<span data-ttu-id="a169c-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a169c-206">win:UInt16</span></span>|<span data-ttu-id="a169c-207">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a169c-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a169c-208">К началу</span><span class="sxs-lookup"><span data-stu-id="a169c-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="a169c-209">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="a169c-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="a169c-210">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="a169c-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a169c-211">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a169c-211">Keyword for raising the event</span></span>|<span data-ttu-id="a169c-212">Уровень</span><span class="sxs-lookup"><span data-stu-id="a169c-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a169c-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a169c-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a169c-214">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-214">Informational(4)</span></span>|  
|<span data-ttu-id="a169c-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a169c-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a169c-216">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="a169c-217">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a169c-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a169c-218">Событие</span><span class="sxs-lookup"><span data-stu-id="a169c-218">Event</span></span>|<span data-ttu-id="a169c-219">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a169c-219">Event ID</span></span>|<span data-ttu-id="a169c-220">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a169c-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="a169c-221">87</span><span class="sxs-lookup"><span data-stu-id="a169c-221">87</span></span>|<span data-ttu-id="a169c-222">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="a169c-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="a169c-223">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a169c-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a169c-224">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a169c-224">Field name</span></span>|<span data-ttu-id="a169c-225">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a169c-225">Data type</span></span>|<span data-ttu-id="a169c-226">Описание</span><span class="sxs-lookup"><span data-stu-id="a169c-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a169c-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a169c-227">ThreadID</span></span>|<span data-ttu-id="a169c-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-228">win:UInt64</span></span>|<span data-ttu-id="a169c-229">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="a169c-229">The thread identifier.</span></span>|  
|<span data-ttu-id="a169c-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a169c-230">AppDomainID</span></span>|<span data-ttu-id="a169c-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-231">win:UInt64</span></span>|<span data-ttu-id="a169c-232">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="a169c-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="a169c-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a169c-233">ClrInstanceID</span></span>|<span data-ttu-id="a169c-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a169c-234">win:UInt16</span></span>|<span data-ttu-id="a169c-235">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a169c-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a169c-236">К началу</span><span class="sxs-lookup"><span data-stu-id="a169c-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="a169c-237">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="a169c-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="a169c-238">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="a169c-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a169c-239">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a169c-239">Keyword for raising the event</span></span>|<span data-ttu-id="a169c-240">Уровень</span><span class="sxs-lookup"><span data-stu-id="a169c-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a169c-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="a169c-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="a169c-242">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-242">Informational(4)</span></span>|  
|<span data-ttu-id="a169c-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a169c-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a169c-244">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a169c-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="a169c-245">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a169c-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a169c-246">Событие</span><span class="sxs-lookup"><span data-stu-id="a169c-246">Event</span></span>|<span data-ttu-id="a169c-247">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a169c-247">Event ID</span></span>|<span data-ttu-id="a169c-248">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a169c-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="a169c-249">86</span><span class="sxs-lookup"><span data-stu-id="a169c-249">86</span></span>|<span data-ttu-id="a169c-250">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="a169c-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="a169c-251">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a169c-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="a169c-252">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a169c-252">Field name</span></span>|<span data-ttu-id="a169c-253">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a169c-253">Data type</span></span>|<span data-ttu-id="a169c-254">Описание</span><span class="sxs-lookup"><span data-stu-id="a169c-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a169c-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="a169c-255">ThreadID</span></span>|<span data-ttu-id="a169c-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-256">win:UInt64</span></span>|<span data-ttu-id="a169c-257">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="a169c-257">The thread identifier.</span></span>|  
|<span data-ttu-id="a169c-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="a169c-258">AppDomainID</span></span>|<span data-ttu-id="a169c-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a169c-259">win:UInt64</span></span>|<span data-ttu-id="a169c-260">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="a169c-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="a169c-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a169c-261">ClrInstanceID</span></span>|<span data-ttu-id="a169c-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a169c-262">win:UInt16</span></span>|<span data-ttu-id="a169c-263">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a169c-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a169c-264">См. также</span><span class="sxs-lookup"><span data-stu-id="a169c-264">See Also</span></span>  
 [<span data-ttu-id="a169c-265">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="a169c-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
