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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133826"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="7404f-102">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="7404f-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="7404f-103">Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7404f-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="7404f-104">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="7404f-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="7404f-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="7404f-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="7404f-106">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="7404f-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="7404f-107">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="7404f-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="7404f-108">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="7404f-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="7404f-109">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="7404f-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="7404f-110">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="7404f-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="7404f-111">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="7404f-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="7404f-112">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="7404f-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="7404f-113">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="7404f-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="7404f-114">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="7404f-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="7404f-115">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="7404f-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="7404f-116">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="7404f-116">Keyword for raising the event</span></span>|<span data-ttu-id="7404f-117">Уровень</span><span class="sxs-lookup"><span data-stu-id="7404f-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7404f-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7404f-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7404f-119">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-119">Informational(4)</span></span>|  
|<span data-ttu-id="7404f-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7404f-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7404f-121">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="7404f-122">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="7404f-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7404f-123">событие</span><span class="sxs-lookup"><span data-stu-id="7404f-123">Event</span></span>|<span data-ttu-id="7404f-124">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7404f-124">Event ID</span></span>|<span data-ttu-id="7404f-125">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="7404f-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="7404f-126">85</span><span class="sxs-lookup"><span data-stu-id="7404f-126">85</span></span>|<span data-ttu-id="7404f-127">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7404f-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="7404f-128">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="7404f-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7404f-129">Имя поля</span><span class="sxs-lookup"><span data-stu-id="7404f-129">Field name</span></span>|<span data-ttu-id="7404f-130">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7404f-130">Data type</span></span>|<span data-ttu-id="7404f-131">Описание</span><span class="sxs-lookup"><span data-stu-id="7404f-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7404f-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="7404f-132">ThreadID</span></span>|<span data-ttu-id="7404f-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-133">win:UInt64</span></span>|<span data-ttu-id="7404f-134">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="7404f-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="7404f-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7404f-135">AppDomainID</span></span>|<span data-ttu-id="7404f-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-136">win:UInt64</span></span>|<span data-ttu-id="7404f-137">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="7404f-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="7404f-138">Флаги</span><span class="sxs-lookup"><span data-stu-id="7404f-138">Flags</span></span>|<span data-ttu-id="7404f-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7404f-139">win:UInt32</span></span>|<span data-ttu-id="7404f-140">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="7404f-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="7404f-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="7404f-141">ManagedThreadIndex</span></span>|<span data-ttu-id="7404f-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7404f-142">win:UInt32</span></span>|<span data-ttu-id="7404f-143">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="7404f-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="7404f-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="7404f-144">OSThreadID</span></span>|<span data-ttu-id="7404f-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7404f-145">win:UInt32</span></span>|<span data-ttu-id="7404f-146">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="7404f-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="7404f-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7404f-147">ClrInstanceID</span></span>|<span data-ttu-id="7404f-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7404f-148">win:UInt16</span></span>|<span data-ttu-id="7404f-149">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7404f-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="7404f-150">К началу</span><span class="sxs-lookup"><span data-stu-id="7404f-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="7404f-151">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="7404f-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="7404f-152">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="7404f-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="7404f-153">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="7404f-153">Keyword for raising the event</span></span>|<span data-ttu-id="7404f-154">Уровень</span><span class="sxs-lookup"><span data-stu-id="7404f-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7404f-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7404f-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7404f-156">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="7404f-157">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="7404f-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7404f-158">событие</span><span class="sxs-lookup"><span data-stu-id="7404f-158">Event</span></span>|<span data-ttu-id="7404f-159">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7404f-159">Event ID</span></span>|<span data-ttu-id="7404f-160">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="7404f-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="7404f-161">83</span><span class="sxs-lookup"><span data-stu-id="7404f-161">83</span></span>|<span data-ttu-id="7404f-162">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="7404f-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="7404f-163">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="7404f-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7404f-164">Имя поля</span><span class="sxs-lookup"><span data-stu-id="7404f-164">Field name</span></span>|<span data-ttu-id="7404f-165">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7404f-165">Data type</span></span>|<span data-ttu-id="7404f-166">Описание</span><span class="sxs-lookup"><span data-stu-id="7404f-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7404f-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7404f-167">AppDomainID</span></span>|<span data-ttu-id="7404f-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-168">win:UInt64</span></span>|<span data-ttu-id="7404f-169">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7404f-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="7404f-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="7404f-170">Allocated</span></span>|<span data-ttu-id="7404f-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-171">win:UInt64</span></span>|<span data-ttu-id="7404f-172">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="7404f-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="7404f-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7404f-173">ClrInstanceID</span></span>|<span data-ttu-id="7404f-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7404f-174">win:UInt16</span></span>|<span data-ttu-id="7404f-175">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7404f-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="7404f-176">К началу</span><span class="sxs-lookup"><span data-stu-id="7404f-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="7404f-177">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="7404f-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="7404f-178">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="7404f-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="7404f-179">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="7404f-179">Keyword for raising the event</span></span>|<span data-ttu-id="7404f-180">Уровень</span><span class="sxs-lookup"><span data-stu-id="7404f-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7404f-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7404f-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7404f-182">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="7404f-183">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="7404f-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7404f-184">событие</span><span class="sxs-lookup"><span data-stu-id="7404f-184">Event</span></span>|<span data-ttu-id="7404f-185">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7404f-185">Event ID</span></span>|<span data-ttu-id="7404f-186">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="7404f-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="7404f-187">84</span><span class="sxs-lookup"><span data-stu-id="7404f-187">84</span></span>|<span data-ttu-id="7404f-188">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="7404f-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="7404f-189">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="7404f-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7404f-190">Имя поля</span><span class="sxs-lookup"><span data-stu-id="7404f-190">Field name</span></span>|<span data-ttu-id="7404f-191">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7404f-191">Data type</span></span>|<span data-ttu-id="7404f-192">Описание</span><span class="sxs-lookup"><span data-stu-id="7404f-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7404f-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7404f-193">AppDomainID</span></span>|<span data-ttu-id="7404f-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-194">win:UInt64</span></span>|<span data-ttu-id="7404f-195">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7404f-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="7404f-196">Survived</span><span class="sxs-lookup"><span data-stu-id="7404f-196">Survived</span></span>|<span data-ttu-id="7404f-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-197">win:UInt64</span></span>|<span data-ttu-id="7404f-198">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="7404f-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="7404f-199">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="7404f-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="7404f-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="7404f-200">ProcessSurvived</span></span>|<span data-ttu-id="7404f-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-201">win:UInt64</span></span>|<span data-ttu-id="7404f-202">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="7404f-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="7404f-203">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="7404f-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="7404f-204">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="7404f-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="7404f-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7404f-205">ClrInstanceID</span></span>|<span data-ttu-id="7404f-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7404f-206">win:UInt16</span></span>|<span data-ttu-id="7404f-207">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7404f-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="7404f-208">К началу</span><span class="sxs-lookup"><span data-stu-id="7404f-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="7404f-209">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="7404f-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="7404f-210">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="7404f-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="7404f-211">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="7404f-211">Keyword for raising the event</span></span>|<span data-ttu-id="7404f-212">Уровень</span><span class="sxs-lookup"><span data-stu-id="7404f-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7404f-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7404f-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7404f-214">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-214">Informational(4)</span></span>|  
|<span data-ttu-id="7404f-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7404f-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7404f-216">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="7404f-217">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="7404f-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7404f-218">событие</span><span class="sxs-lookup"><span data-stu-id="7404f-218">Event</span></span>|<span data-ttu-id="7404f-219">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7404f-219">Event ID</span></span>|<span data-ttu-id="7404f-220">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="7404f-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="7404f-221">87</span><span class="sxs-lookup"><span data-stu-id="7404f-221">87</span></span>|<span data-ttu-id="7404f-222">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="7404f-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="7404f-223">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="7404f-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7404f-224">Имя поля</span><span class="sxs-lookup"><span data-stu-id="7404f-224">Field name</span></span>|<span data-ttu-id="7404f-225">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7404f-225">Data type</span></span>|<span data-ttu-id="7404f-226">Описание</span><span class="sxs-lookup"><span data-stu-id="7404f-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7404f-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="7404f-227">ThreadID</span></span>|<span data-ttu-id="7404f-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-228">win:UInt64</span></span>|<span data-ttu-id="7404f-229">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="7404f-229">The thread identifier.</span></span>|  
|<span data-ttu-id="7404f-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7404f-230">AppDomainID</span></span>|<span data-ttu-id="7404f-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-231">win:UInt64</span></span>|<span data-ttu-id="7404f-232">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7404f-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="7404f-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7404f-233">ClrInstanceID</span></span>|<span data-ttu-id="7404f-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7404f-234">win:UInt16</span></span>|<span data-ttu-id="7404f-235">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7404f-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="7404f-236">К началу</span><span class="sxs-lookup"><span data-stu-id="7404f-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="7404f-237">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="7404f-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="7404f-238">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="7404f-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="7404f-239">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="7404f-239">Keyword for raising the event</span></span>|<span data-ttu-id="7404f-240">Уровень</span><span class="sxs-lookup"><span data-stu-id="7404f-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7404f-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="7404f-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="7404f-242">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-242">Informational(4)</span></span>|  
|<span data-ttu-id="7404f-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="7404f-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="7404f-244">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="7404f-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="7404f-245">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="7404f-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7404f-246">событие</span><span class="sxs-lookup"><span data-stu-id="7404f-246">Event</span></span>|<span data-ttu-id="7404f-247">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="7404f-247">Event ID</span></span>|<span data-ttu-id="7404f-248">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="7404f-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="7404f-249">86</span><span class="sxs-lookup"><span data-stu-id="7404f-249">86</span></span>|<span data-ttu-id="7404f-250">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="7404f-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="7404f-251">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="7404f-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="7404f-252">Имя поля</span><span class="sxs-lookup"><span data-stu-id="7404f-252">Field name</span></span>|<span data-ttu-id="7404f-253">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7404f-253">Data type</span></span>|<span data-ttu-id="7404f-254">Описание</span><span class="sxs-lookup"><span data-stu-id="7404f-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7404f-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="7404f-255">ThreadID</span></span>|<span data-ttu-id="7404f-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-256">win:UInt64</span></span>|<span data-ttu-id="7404f-257">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="7404f-257">The thread identifier.</span></span>|  
|<span data-ttu-id="7404f-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="7404f-258">AppDomainID</span></span>|<span data-ttu-id="7404f-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="7404f-259">win:UInt64</span></span>|<span data-ttu-id="7404f-260">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7404f-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="7404f-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7404f-261">ClrInstanceID</span></span>|<span data-ttu-id="7404f-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7404f-262">win:UInt16</span></span>|<span data-ttu-id="7404f-263">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7404f-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7404f-264">См. также</span><span class="sxs-lookup"><span data-stu-id="7404f-264">See also</span></span>

- [<span data-ttu-id="7404f-265">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="7404f-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
