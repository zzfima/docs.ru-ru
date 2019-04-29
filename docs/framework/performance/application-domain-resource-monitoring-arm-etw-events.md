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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788067"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="41a0b-102">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="41a0b-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="41a0b-103">Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="41a0b-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="41a0b-104">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="41a0b-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="41a0b-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="41a0b-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="41a0b-106">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="41a0b-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="41a0b-107">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="41a0b-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="41a0b-108">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="41a0b-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="41a0b-109">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="41a0b-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="41a0b-110">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="41a0b-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="41a0b-111">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="41a0b-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="41a0b-112">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="41a0b-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="41a0b-113">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="41a0b-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="41a0b-114">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="41a0b-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="41a0b-115">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="41a0b-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="41a0b-116">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="41a0b-116">Keyword for raising the event</span></span>|<span data-ttu-id="41a0b-117">Уровень</span><span class="sxs-lookup"><span data-stu-id="41a0b-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="41a0b-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="41a0b-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="41a0b-119">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-119">Informational(4)</span></span>|  
|<span data-ttu-id="41a0b-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="41a0b-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="41a0b-121">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="41a0b-122">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="41a0b-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="41a0b-123">событие</span><span class="sxs-lookup"><span data-stu-id="41a0b-123">Event</span></span>|<span data-ttu-id="41a0b-124">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="41a0b-124">Event ID</span></span>|<span data-ttu-id="41a0b-125">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="41a0b-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="41a0b-126">85</span><span class="sxs-lookup"><span data-stu-id="41a0b-126">85</span></span>|<span data-ttu-id="41a0b-127">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="41a0b-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="41a0b-128">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="41a0b-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="41a0b-129">Имя поля</span><span class="sxs-lookup"><span data-stu-id="41a0b-129">Field name</span></span>|<span data-ttu-id="41a0b-130">Тип данных</span><span class="sxs-lookup"><span data-stu-id="41a0b-130">Data type</span></span>|<span data-ttu-id="41a0b-131">Описание</span><span class="sxs-lookup"><span data-stu-id="41a0b-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="41a0b-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="41a0b-132">ThreadID</span></span>|<span data-ttu-id="41a0b-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-133">win:UInt64</span></span>|<span data-ttu-id="41a0b-134">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="41a0b-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="41a0b-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="41a0b-135">AppDomainID</span></span>|<span data-ttu-id="41a0b-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-136">win:UInt64</span></span>|<span data-ttu-id="41a0b-137">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="41a0b-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="41a0b-138">Флаги</span><span class="sxs-lookup"><span data-stu-id="41a0b-138">Flags</span></span>|<span data-ttu-id="41a0b-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="41a0b-139">win:UInt32</span></span>|<span data-ttu-id="41a0b-140">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="41a0b-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="41a0b-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="41a0b-141">ManagedThreadIndex</span></span>|<span data-ttu-id="41a0b-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="41a0b-142">win:UInt32</span></span>|<span data-ttu-id="41a0b-143">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="41a0b-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="41a0b-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="41a0b-144">OSThreadID</span></span>|<span data-ttu-id="41a0b-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="41a0b-145">win:UInt32</span></span>|<span data-ttu-id="41a0b-146">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="41a0b-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="41a0b-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="41a0b-147">ClrInstanceID</span></span>|<span data-ttu-id="41a0b-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="41a0b-148">win:UInt16</span></span>|<span data-ttu-id="41a0b-149">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="41a0b-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="41a0b-150">К началу</span><span class="sxs-lookup"><span data-stu-id="41a0b-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="41a0b-151">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="41a0b-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="41a0b-152">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="41a0b-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="41a0b-153">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="41a0b-153">Keyword for raising the event</span></span>|<span data-ttu-id="41a0b-154">Уровень</span><span class="sxs-lookup"><span data-stu-id="41a0b-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="41a0b-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="41a0b-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="41a0b-156">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="41a0b-157">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="41a0b-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="41a0b-158">событие</span><span class="sxs-lookup"><span data-stu-id="41a0b-158">Event</span></span>|<span data-ttu-id="41a0b-159">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="41a0b-159">Event ID</span></span>|<span data-ttu-id="41a0b-160">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="41a0b-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="41a0b-161">83</span><span class="sxs-lookup"><span data-stu-id="41a0b-161">83</span></span>|<span data-ttu-id="41a0b-162">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="41a0b-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="41a0b-163">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="41a0b-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="41a0b-164">Имя поля</span><span class="sxs-lookup"><span data-stu-id="41a0b-164">Field name</span></span>|<span data-ttu-id="41a0b-165">Тип данных</span><span class="sxs-lookup"><span data-stu-id="41a0b-165">Data type</span></span>|<span data-ttu-id="41a0b-166">Описание</span><span class="sxs-lookup"><span data-stu-id="41a0b-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="41a0b-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="41a0b-167">AppDomainID</span></span>|<span data-ttu-id="41a0b-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-168">win:UInt64</span></span>|<span data-ttu-id="41a0b-169">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="41a0b-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="41a0b-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="41a0b-170">Allocated</span></span>|<span data-ttu-id="41a0b-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-171">win:UInt64</span></span>|<span data-ttu-id="41a0b-172">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="41a0b-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="41a0b-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="41a0b-173">ClrInstanceID</span></span>|<span data-ttu-id="41a0b-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="41a0b-174">win:UInt16</span></span>|<span data-ttu-id="41a0b-175">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="41a0b-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="41a0b-176">К началу</span><span class="sxs-lookup"><span data-stu-id="41a0b-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="41a0b-177">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="41a0b-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="41a0b-178">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="41a0b-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="41a0b-179">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="41a0b-179">Keyword for raising the event</span></span>|<span data-ttu-id="41a0b-180">Уровень</span><span class="sxs-lookup"><span data-stu-id="41a0b-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="41a0b-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="41a0b-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="41a0b-182">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="41a0b-183">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="41a0b-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="41a0b-184">событие</span><span class="sxs-lookup"><span data-stu-id="41a0b-184">Event</span></span>|<span data-ttu-id="41a0b-185">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="41a0b-185">Event ID</span></span>|<span data-ttu-id="41a0b-186">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="41a0b-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="41a0b-187">84</span><span class="sxs-lookup"><span data-stu-id="41a0b-187">84</span></span>|<span data-ttu-id="41a0b-188">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="41a0b-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="41a0b-189">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="41a0b-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="41a0b-190">Имя поля</span><span class="sxs-lookup"><span data-stu-id="41a0b-190">Field name</span></span>|<span data-ttu-id="41a0b-191">Тип данных</span><span class="sxs-lookup"><span data-stu-id="41a0b-191">Data type</span></span>|<span data-ttu-id="41a0b-192">Описание</span><span class="sxs-lookup"><span data-stu-id="41a0b-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="41a0b-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="41a0b-193">AppDomainID</span></span>|<span data-ttu-id="41a0b-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-194">win:UInt64</span></span>|<span data-ttu-id="41a0b-195">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="41a0b-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="41a0b-196">Survived</span><span class="sxs-lookup"><span data-stu-id="41a0b-196">Survived</span></span>|<span data-ttu-id="41a0b-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-197">win:UInt64</span></span>|<span data-ttu-id="41a0b-198">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="41a0b-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="41a0b-199">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="41a0b-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="41a0b-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="41a0b-200">ProcessSurvived</span></span>|<span data-ttu-id="41a0b-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-201">win:UInt64</span></span>|<span data-ttu-id="41a0b-202">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="41a0b-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="41a0b-203">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="41a0b-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="41a0b-204">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="41a0b-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="41a0b-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="41a0b-205">ClrInstanceID</span></span>|<span data-ttu-id="41a0b-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="41a0b-206">win:UInt16</span></span>|<span data-ttu-id="41a0b-207">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="41a0b-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="41a0b-208">К началу</span><span class="sxs-lookup"><span data-stu-id="41a0b-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="41a0b-209">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="41a0b-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="41a0b-210">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="41a0b-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="41a0b-211">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="41a0b-211">Keyword for raising the event</span></span>|<span data-ttu-id="41a0b-212">Уровень</span><span class="sxs-lookup"><span data-stu-id="41a0b-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="41a0b-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="41a0b-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="41a0b-214">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-214">Informational(4)</span></span>|  
|<span data-ttu-id="41a0b-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="41a0b-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="41a0b-216">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="41a0b-217">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="41a0b-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="41a0b-218">событие</span><span class="sxs-lookup"><span data-stu-id="41a0b-218">Event</span></span>|<span data-ttu-id="41a0b-219">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="41a0b-219">Event ID</span></span>|<span data-ttu-id="41a0b-220">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="41a0b-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="41a0b-221">87</span><span class="sxs-lookup"><span data-stu-id="41a0b-221">87</span></span>|<span data-ttu-id="41a0b-222">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="41a0b-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="41a0b-223">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="41a0b-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="41a0b-224">Имя поля</span><span class="sxs-lookup"><span data-stu-id="41a0b-224">Field name</span></span>|<span data-ttu-id="41a0b-225">Тип данных</span><span class="sxs-lookup"><span data-stu-id="41a0b-225">Data type</span></span>|<span data-ttu-id="41a0b-226">Описание</span><span class="sxs-lookup"><span data-stu-id="41a0b-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="41a0b-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="41a0b-227">ThreadID</span></span>|<span data-ttu-id="41a0b-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-228">win:UInt64</span></span>|<span data-ttu-id="41a0b-229">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="41a0b-229">The thread identifier.</span></span>|  
|<span data-ttu-id="41a0b-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="41a0b-230">AppDomainID</span></span>|<span data-ttu-id="41a0b-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-231">win:UInt64</span></span>|<span data-ttu-id="41a0b-232">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="41a0b-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="41a0b-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="41a0b-233">ClrInstanceID</span></span>|<span data-ttu-id="41a0b-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="41a0b-234">win:UInt16</span></span>|<span data-ttu-id="41a0b-235">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="41a0b-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="41a0b-236">К началу</span><span class="sxs-lookup"><span data-stu-id="41a0b-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="41a0b-237">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="41a0b-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="41a0b-238">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="41a0b-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="41a0b-239">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="41a0b-239">Keyword for raising the event</span></span>|<span data-ttu-id="41a0b-240">Уровень</span><span class="sxs-lookup"><span data-stu-id="41a0b-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="41a0b-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="41a0b-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="41a0b-242">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-242">Informational(4)</span></span>|  
|<span data-ttu-id="41a0b-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="41a0b-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="41a0b-244">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="41a0b-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="41a0b-245">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="41a0b-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="41a0b-246">событие</span><span class="sxs-lookup"><span data-stu-id="41a0b-246">Event</span></span>|<span data-ttu-id="41a0b-247">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="41a0b-247">Event ID</span></span>|<span data-ttu-id="41a0b-248">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="41a0b-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="41a0b-249">86</span><span class="sxs-lookup"><span data-stu-id="41a0b-249">86</span></span>|<span data-ttu-id="41a0b-250">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="41a0b-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="41a0b-251">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="41a0b-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="41a0b-252">Имя поля</span><span class="sxs-lookup"><span data-stu-id="41a0b-252">Field name</span></span>|<span data-ttu-id="41a0b-253">Тип данных</span><span class="sxs-lookup"><span data-stu-id="41a0b-253">Data type</span></span>|<span data-ttu-id="41a0b-254">Описание</span><span class="sxs-lookup"><span data-stu-id="41a0b-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="41a0b-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="41a0b-255">ThreadID</span></span>|<span data-ttu-id="41a0b-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-256">win:UInt64</span></span>|<span data-ttu-id="41a0b-257">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="41a0b-257">The thread identifier.</span></span>|  
|<span data-ttu-id="41a0b-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="41a0b-258">AppDomainID</span></span>|<span data-ttu-id="41a0b-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="41a0b-259">win:UInt64</span></span>|<span data-ttu-id="41a0b-260">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="41a0b-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="41a0b-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="41a0b-261">ClrInstanceID</span></span>|<span data-ttu-id="41a0b-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="41a0b-262">win:UInt16</span></span>|<span data-ttu-id="41a0b-263">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="41a0b-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41a0b-264">См. также</span><span class="sxs-lookup"><span data-stu-id="41a0b-264">See also</span></span>

- [<span data-ttu-id="41a0b-265">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="41a0b-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
