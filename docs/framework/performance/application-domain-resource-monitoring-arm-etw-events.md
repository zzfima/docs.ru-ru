---
title: События отслеживания ресурсов домена приложения (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bb2b0dd95877fc6492f6d23a19c14688cd78f7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133826"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="c426e-102">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="c426e-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="c426e-103">Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c426e-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="c426e-104">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="c426e-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="c426e-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="c426e-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="c426e-106">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="c426e-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="c426e-107">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="c426e-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="c426e-108">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="c426e-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="c426e-109">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="c426e-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="c426e-110">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="c426e-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="c426e-111">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="c426e-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="c426e-112">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="c426e-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="c426e-113">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="c426e-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="c426e-114">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="c426e-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="c426e-115">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="c426e-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c426e-116">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="c426e-116">Keyword for raising the event</span></span>|<span data-ttu-id="c426e-117">Уровень</span><span class="sxs-lookup"><span data-stu-id="c426e-117">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c426e-118">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c426e-118">(0x800)</span></span>|<span data-ttu-id="c426e-119">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-119">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="c426e-120">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="c426e-120">(0x10000)</span></span>|<span data-ttu-id="c426e-121">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="c426e-122">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="c426e-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c426e-123">событие</span><span class="sxs-lookup"><span data-stu-id="c426e-123">Event</span></span>|<span data-ttu-id="c426e-124">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c426e-124">Event ID</span></span>|<span data-ttu-id="c426e-125">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="c426e-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="c426e-126">85</span><span class="sxs-lookup"><span data-stu-id="c426e-126">85</span></span>|<span data-ttu-id="c426e-127">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c426e-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="c426e-128">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="c426e-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c426e-129">Имя поля</span><span class="sxs-lookup"><span data-stu-id="c426e-129">Field name</span></span>|<span data-ttu-id="c426e-130">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c426e-130">Data type</span></span>|<span data-ttu-id="c426e-131">Описание</span><span class="sxs-lookup"><span data-stu-id="c426e-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c426e-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="c426e-132">ThreadID</span></span>|<span data-ttu-id="c426e-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-133">win:UInt64</span></span>|<span data-ttu-id="c426e-134">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="c426e-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="c426e-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c426e-135">AppDomainID</span></span>|<span data-ttu-id="c426e-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-136">win:UInt64</span></span>|<span data-ttu-id="c426e-137">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="c426e-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="c426e-138">Флаги</span><span class="sxs-lookup"><span data-stu-id="c426e-138">Flags</span></span>|<span data-ttu-id="c426e-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c426e-139">win:UInt32</span></span>|<span data-ttu-id="c426e-140">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="c426e-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="c426e-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="c426e-141">ManagedThreadIndex</span></span>|<span data-ttu-id="c426e-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c426e-142">win:UInt32</span></span>|<span data-ttu-id="c426e-143">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="c426e-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="c426e-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="c426e-144">OSThreadID</span></span>|<span data-ttu-id="c426e-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c426e-145">win:UInt32</span></span>|<span data-ttu-id="c426e-146">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="c426e-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="c426e-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c426e-147">ClrInstanceID</span></span>|<span data-ttu-id="c426e-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c426e-148">win:UInt16</span></span>|<span data-ttu-id="c426e-149">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c426e-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c426e-150">К началу</span><span class="sxs-lookup"><span data-stu-id="c426e-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="c426e-151">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="c426e-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="c426e-152">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="c426e-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c426e-153">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="c426e-153">Keyword for raising the event</span></span>|<span data-ttu-id="c426e-154">Уровень</span><span class="sxs-lookup"><span data-stu-id="c426e-154">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c426e-155">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c426e-155">(0x800)</span></span>|<span data-ttu-id="c426e-156">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="c426e-157">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="c426e-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c426e-158">событие</span><span class="sxs-lookup"><span data-stu-id="c426e-158">Event</span></span>|<span data-ttu-id="c426e-159">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c426e-159">Event ID</span></span>|<span data-ttu-id="c426e-160">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="c426e-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="c426e-161">83</span><span class="sxs-lookup"><span data-stu-id="c426e-161">83</span></span>|<span data-ttu-id="c426e-162">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="c426e-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="c426e-163">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="c426e-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c426e-164">Имя поля</span><span class="sxs-lookup"><span data-stu-id="c426e-164">Field name</span></span>|<span data-ttu-id="c426e-165">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c426e-165">Data type</span></span>|<span data-ttu-id="c426e-166">Описание</span><span class="sxs-lookup"><span data-stu-id="c426e-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c426e-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c426e-167">AppDomainID</span></span>|<span data-ttu-id="c426e-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-168">win:UInt64</span></span>|<span data-ttu-id="c426e-169">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c426e-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="c426e-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="c426e-170">Allocated</span></span>|<span data-ttu-id="c426e-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-171">win:UInt64</span></span>|<span data-ttu-id="c426e-172">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="c426e-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="c426e-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c426e-173">ClrInstanceID</span></span>|<span data-ttu-id="c426e-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c426e-174">win:UInt16</span></span>|<span data-ttu-id="c426e-175">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c426e-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c426e-176">К началу</span><span class="sxs-lookup"><span data-stu-id="c426e-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="c426e-177">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="c426e-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="c426e-178">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="c426e-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c426e-179">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="c426e-179">Keyword for raising the event</span></span>|<span data-ttu-id="c426e-180">Уровень</span><span class="sxs-lookup"><span data-stu-id="c426e-180">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c426e-181">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c426e-181">(0x800)</span></span>|<span data-ttu-id="c426e-182">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="c426e-183">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="c426e-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c426e-184">событие</span><span class="sxs-lookup"><span data-stu-id="c426e-184">Event</span></span>|<span data-ttu-id="c426e-185">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c426e-185">Event ID</span></span>|<span data-ttu-id="c426e-186">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="c426e-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="c426e-187">84</span><span class="sxs-lookup"><span data-stu-id="c426e-187">84</span></span>|<span data-ttu-id="c426e-188">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="c426e-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="c426e-189">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="c426e-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c426e-190">Имя поля</span><span class="sxs-lookup"><span data-stu-id="c426e-190">Field name</span></span>|<span data-ttu-id="c426e-191">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c426e-191">Data type</span></span>|<span data-ttu-id="c426e-192">Описание</span><span class="sxs-lookup"><span data-stu-id="c426e-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c426e-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c426e-193">AppDomainID</span></span>|<span data-ttu-id="c426e-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-194">win:UInt64</span></span>|<span data-ttu-id="c426e-195">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c426e-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="c426e-196">Survived</span><span class="sxs-lookup"><span data-stu-id="c426e-196">Survived</span></span>|<span data-ttu-id="c426e-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-197">win:UInt64</span></span>|<span data-ttu-id="c426e-198">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="c426e-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="c426e-199">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="c426e-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="c426e-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="c426e-200">ProcessSurvived</span></span>|<span data-ttu-id="c426e-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-201">win:UInt64</span></span>|<span data-ttu-id="c426e-202">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c426e-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="c426e-203">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="c426e-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="c426e-204">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="c426e-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="c426e-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c426e-205">ClrInstanceID</span></span>|<span data-ttu-id="c426e-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c426e-206">win:UInt16</span></span>|<span data-ttu-id="c426e-207">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c426e-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c426e-208">К началу</span><span class="sxs-lookup"><span data-stu-id="c426e-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="c426e-209">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="c426e-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="c426e-210">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="c426e-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c426e-211">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="c426e-211">Keyword for raising the event</span></span>|<span data-ttu-id="c426e-212">Уровень</span><span class="sxs-lookup"><span data-stu-id="c426e-212">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c426e-213">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c426e-213">(0x800)</span></span>|<span data-ttu-id="c426e-214">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-214">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="c426e-215">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="c426e-215">(0x10000)</span></span>|<span data-ttu-id="c426e-216">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="c426e-217">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="c426e-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c426e-218">событие</span><span class="sxs-lookup"><span data-stu-id="c426e-218">Event</span></span>|<span data-ttu-id="c426e-219">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c426e-219">Event ID</span></span>|<span data-ttu-id="c426e-220">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="c426e-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="c426e-221">87</span><span class="sxs-lookup"><span data-stu-id="c426e-221">87</span></span>|<span data-ttu-id="c426e-222">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="c426e-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="c426e-223">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="c426e-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c426e-224">Имя поля</span><span class="sxs-lookup"><span data-stu-id="c426e-224">Field name</span></span>|<span data-ttu-id="c426e-225">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c426e-225">Data type</span></span>|<span data-ttu-id="c426e-226">Описание</span><span class="sxs-lookup"><span data-stu-id="c426e-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c426e-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="c426e-227">ThreadID</span></span>|<span data-ttu-id="c426e-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-228">win:UInt64</span></span>|<span data-ttu-id="c426e-229">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="c426e-229">The thread identifier.</span></span>|  
|<span data-ttu-id="c426e-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c426e-230">AppDomainID</span></span>|<span data-ttu-id="c426e-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-231">win:UInt64</span></span>|<span data-ttu-id="c426e-232">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c426e-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="c426e-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c426e-233">ClrInstanceID</span></span>|<span data-ttu-id="c426e-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c426e-234">win:UInt16</span></span>|<span data-ttu-id="c426e-235">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c426e-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c426e-236">К началу</span><span class="sxs-lookup"><span data-stu-id="c426e-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="c426e-237">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="c426e-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="c426e-238">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="c426e-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c426e-239">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="c426e-239">Keyword for raising the event</span></span>|<span data-ttu-id="c426e-240">Уровень</span><span class="sxs-lookup"><span data-stu-id="c426e-240">Level</span></span>|  
|-----------------------------------|-----------|  
|`AppDomainResourceManagementKeyword` <span data-ttu-id="c426e-241">(0x800)</span><span class="sxs-lookup"><span data-stu-id="c426e-241">(0x800)</span></span>|<span data-ttu-id="c426e-242">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-242">Informational(4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="c426e-243">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="c426e-243">(0x10000)</span></span>|<span data-ttu-id="c426e-244">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="c426e-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="c426e-245">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="c426e-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c426e-246">событие</span><span class="sxs-lookup"><span data-stu-id="c426e-246">Event</span></span>|<span data-ttu-id="c426e-247">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c426e-247">Event ID</span></span>|<span data-ttu-id="c426e-248">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="c426e-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="c426e-249">86</span><span class="sxs-lookup"><span data-stu-id="c426e-249">86</span></span>|<span data-ttu-id="c426e-250">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="c426e-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="c426e-251">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="c426e-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="c426e-252">Имя поля</span><span class="sxs-lookup"><span data-stu-id="c426e-252">Field name</span></span>|<span data-ttu-id="c426e-253">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c426e-253">Data type</span></span>|<span data-ttu-id="c426e-254">Описание</span><span class="sxs-lookup"><span data-stu-id="c426e-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c426e-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="c426e-255">ThreadID</span></span>|<span data-ttu-id="c426e-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-256">win:UInt64</span></span>|<span data-ttu-id="c426e-257">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="c426e-257">The thread identifier.</span></span>|  
|<span data-ttu-id="c426e-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="c426e-258">AppDomainID</span></span>|<span data-ttu-id="c426e-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c426e-259">win:UInt64</span></span>|<span data-ttu-id="c426e-260">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c426e-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="c426e-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c426e-261">ClrInstanceID</span></span>|<span data-ttu-id="c426e-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c426e-262">win:UInt16</span></span>|<span data-ttu-id="c426e-263">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c426e-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c426e-264">См. также</span><span class="sxs-lookup"><span data-stu-id="c426e-264">See also</span></span>

- [<span data-ttu-id="c426e-265">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="c426e-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
