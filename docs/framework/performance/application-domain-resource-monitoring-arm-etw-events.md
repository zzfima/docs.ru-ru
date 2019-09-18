---
title: События отслеживания ресурсов домена приложения (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e4002ae248022a9e4380c79174109494b5e4ca
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046771"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="0fd2a-102">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="0fd2a-103">Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="0fd2a-104">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="0fd2a-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="0fd2a-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="0fd2a-106">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="0fd2a-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="0fd2a-107">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="0fd2a-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="0fd2a-108">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="0fd2a-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="0fd2a-109">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="0fd2a-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="0fd2a-110">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="0fd2a-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="0fd2a-111">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="0fd2a-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="0fd2a-112">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="0fd2a-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="0fd2a-113">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="0fd2a-114">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="0fd2a-115">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="0fd2a-116">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-116">Keyword for raising the event</span></span>|<span data-ttu-id="0fd2a-117">Уровень</span><span class="sxs-lookup"><span data-stu-id="0fd2a-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0fd2a-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="0fd2a-119">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-119">Informational(4)</span></span>|  
|<span data-ttu-id="0fd2a-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="0fd2a-121">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="0fd2a-122">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0fd2a-123">событие</span><span class="sxs-lookup"><span data-stu-id="0fd2a-123">Event</span></span>|<span data-ttu-id="0fd2a-124">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-124">Event ID</span></span>|<span data-ttu-id="0fd2a-125">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="0fd2a-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="0fd2a-126">85</span><span class="sxs-lookup"><span data-stu-id="0fd2a-126">85</span></span>|<span data-ttu-id="0fd2a-127">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="0fd2a-128">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0fd2a-129">Имя поля</span><span class="sxs-lookup"><span data-stu-id="0fd2a-129">Field name</span></span>|<span data-ttu-id="0fd2a-130">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0fd2a-130">Data type</span></span>|<span data-ttu-id="0fd2a-131">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd2a-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0fd2a-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-132">ThreadID</span></span>|<span data-ttu-id="0fd2a-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-133">win:UInt64</span></span>|<span data-ttu-id="0fd2a-134">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="0fd2a-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-135">AppDomainID</span></span>|<span data-ttu-id="0fd2a-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-136">win:UInt64</span></span>|<span data-ttu-id="0fd2a-137">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="0fd2a-138">Флаги</span><span class="sxs-lookup"><span data-stu-id="0fd2a-138">Flags</span></span>|<span data-ttu-id="0fd2a-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0fd2a-139">win:UInt32</span></span>|<span data-ttu-id="0fd2a-140">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="0fd2a-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="0fd2a-141">ManagedThreadIndex</span></span>|<span data-ttu-id="0fd2a-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0fd2a-142">win:UInt32</span></span>|<span data-ttu-id="0fd2a-143">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="0fd2a-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-144">OSThreadID</span></span>|<span data-ttu-id="0fd2a-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="0fd2a-145">win:UInt32</span></span>|<span data-ttu-id="0fd2a-146">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="0fd2a-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-147">ClrInstanceID</span></span>|<span data-ttu-id="0fd2a-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0fd2a-148">win:UInt16</span></span>|<span data-ttu-id="0fd2a-149">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0fd2a-150">К началу</span><span class="sxs-lookup"><span data-stu-id="0fd2a-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="0fd2a-151">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="0fd2a-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="0fd2a-152">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0fd2a-153">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-153">Keyword for raising the event</span></span>|<span data-ttu-id="0fd2a-154">Уровень</span><span class="sxs-lookup"><span data-stu-id="0fd2a-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0fd2a-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="0fd2a-156">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="0fd2a-157">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0fd2a-158">событие</span><span class="sxs-lookup"><span data-stu-id="0fd2a-158">Event</span></span>|<span data-ttu-id="0fd2a-159">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-159">Event ID</span></span>|<span data-ttu-id="0fd2a-160">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="0fd2a-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="0fd2a-161">83</span><span class="sxs-lookup"><span data-stu-id="0fd2a-161">83</span></span>|<span data-ttu-id="0fd2a-162">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="0fd2a-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="0fd2a-163">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0fd2a-164">Имя поля</span><span class="sxs-lookup"><span data-stu-id="0fd2a-164">Field name</span></span>|<span data-ttu-id="0fd2a-165">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0fd2a-165">Data type</span></span>|<span data-ttu-id="0fd2a-166">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd2a-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0fd2a-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-167">AppDomainID</span></span>|<span data-ttu-id="0fd2a-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-168">win:UInt64</span></span>|<span data-ttu-id="0fd2a-169">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="0fd2a-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="0fd2a-170">Allocated</span></span>|<span data-ttu-id="0fd2a-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-171">win:UInt64</span></span>|<span data-ttu-id="0fd2a-172">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="0fd2a-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="0fd2a-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-173">ClrInstanceID</span></span>|<span data-ttu-id="0fd2a-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0fd2a-174">win:UInt16</span></span>|<span data-ttu-id="0fd2a-175">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0fd2a-176">К началу</span><span class="sxs-lookup"><span data-stu-id="0fd2a-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="0fd2a-177">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="0fd2a-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="0fd2a-178">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0fd2a-179">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-179">Keyword for raising the event</span></span>|<span data-ttu-id="0fd2a-180">Уровень</span><span class="sxs-lookup"><span data-stu-id="0fd2a-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0fd2a-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="0fd2a-182">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="0fd2a-183">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0fd2a-184">событие</span><span class="sxs-lookup"><span data-stu-id="0fd2a-184">Event</span></span>|<span data-ttu-id="0fd2a-185">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-185">Event ID</span></span>|<span data-ttu-id="0fd2a-186">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="0fd2a-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="0fd2a-187">84</span><span class="sxs-lookup"><span data-stu-id="0fd2a-187">84</span></span>|<span data-ttu-id="0fd2a-188">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="0fd2a-189">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0fd2a-190">Имя поля</span><span class="sxs-lookup"><span data-stu-id="0fd2a-190">Field name</span></span>|<span data-ttu-id="0fd2a-191">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0fd2a-191">Data type</span></span>|<span data-ttu-id="0fd2a-192">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd2a-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0fd2a-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-193">AppDomainID</span></span>|<span data-ttu-id="0fd2a-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-194">win:UInt64</span></span>|<span data-ttu-id="0fd2a-195">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="0fd2a-196">Survived</span><span class="sxs-lookup"><span data-stu-id="0fd2a-196">Survived</span></span>|<span data-ttu-id="0fd2a-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-197">win:UInt64</span></span>|<span data-ttu-id="0fd2a-198">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="0fd2a-199">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="0fd2a-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="0fd2a-200">ProcessSurvived</span></span>|<span data-ttu-id="0fd2a-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-201">win:UInt64</span></span>|<span data-ttu-id="0fd2a-202">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="0fd2a-203">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="0fd2a-204">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="0fd2a-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-205">ClrInstanceID</span></span>|<span data-ttu-id="0fd2a-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0fd2a-206">win:UInt16</span></span>|<span data-ttu-id="0fd2a-207">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0fd2a-208">К началу</span><span class="sxs-lookup"><span data-stu-id="0fd2a-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="0fd2a-209">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="0fd2a-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="0fd2a-210">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0fd2a-211">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-211">Keyword for raising the event</span></span>|<span data-ttu-id="0fd2a-212">Уровень</span><span class="sxs-lookup"><span data-stu-id="0fd2a-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0fd2a-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="0fd2a-214">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-214">Informational(4)</span></span>|  
|<span data-ttu-id="0fd2a-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="0fd2a-216">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="0fd2a-217">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0fd2a-218">событие</span><span class="sxs-lookup"><span data-stu-id="0fd2a-218">Event</span></span>|<span data-ttu-id="0fd2a-219">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-219">Event ID</span></span>|<span data-ttu-id="0fd2a-220">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="0fd2a-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="0fd2a-221">87</span><span class="sxs-lookup"><span data-stu-id="0fd2a-221">87</span></span>|<span data-ttu-id="0fd2a-222">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="0fd2a-223">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="0fd2a-224">Имя поля</span><span class="sxs-lookup"><span data-stu-id="0fd2a-224">Field name</span></span>|<span data-ttu-id="0fd2a-225">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0fd2a-225">Data type</span></span>|<span data-ttu-id="0fd2a-226">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd2a-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0fd2a-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-227">ThreadID</span></span>|<span data-ttu-id="0fd2a-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-228">win:UInt64</span></span>|<span data-ttu-id="0fd2a-229">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-229">The thread identifier.</span></span>|  
|<span data-ttu-id="0fd2a-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-230">AppDomainID</span></span>|<span data-ttu-id="0fd2a-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-231">win:UInt64</span></span>|<span data-ttu-id="0fd2a-232">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="0fd2a-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-233">ClrInstanceID</span></span>|<span data-ttu-id="0fd2a-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0fd2a-234">win:UInt16</span></span>|<span data-ttu-id="0fd2a-235">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="0fd2a-236">К началу</span><span class="sxs-lookup"><span data-stu-id="0fd2a-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="0fd2a-237">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="0fd2a-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="0fd2a-238">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="0fd2a-239">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-239">Keyword for raising the event</span></span>|<span data-ttu-id="0fd2a-240">Уровень</span><span class="sxs-lookup"><span data-stu-id="0fd2a-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="0fd2a-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="0fd2a-242">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-242">Informational(4)</span></span>|  
|<span data-ttu-id="0fd2a-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="0fd2a-244">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="0fd2a-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="0fd2a-245">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="0fd2a-246">событие</span><span class="sxs-lookup"><span data-stu-id="0fd2a-246">Event</span></span>|<span data-ttu-id="0fd2a-247">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0fd2a-247">Event ID</span></span>|<span data-ttu-id="0fd2a-248">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="0fd2a-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="0fd2a-249">86</span><span class="sxs-lookup"><span data-stu-id="0fd2a-249">86</span></span>|<span data-ttu-id="0fd2a-250">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="0fd2a-251">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="0fd2a-252">Имя поля</span><span class="sxs-lookup"><span data-stu-id="0fd2a-252">Field name</span></span>|<span data-ttu-id="0fd2a-253">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0fd2a-253">Data type</span></span>|<span data-ttu-id="0fd2a-254">Описание</span><span class="sxs-lookup"><span data-stu-id="0fd2a-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="0fd2a-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-255">ThreadID</span></span>|<span data-ttu-id="0fd2a-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-256">win:UInt64</span></span>|<span data-ttu-id="0fd2a-257">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-257">The thread identifier.</span></span>|  
|<span data-ttu-id="0fd2a-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-258">AppDomainID</span></span>|<span data-ttu-id="0fd2a-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="0fd2a-259">win:UInt64</span></span>|<span data-ttu-id="0fd2a-260">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="0fd2a-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="0fd2a-261">ClrInstanceID</span></span>|<span data-ttu-id="0fd2a-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="0fd2a-262">win:UInt16</span></span>|<span data-ttu-id="0fd2a-263">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="0fd2a-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fd2a-264">См. также</span><span class="sxs-lookup"><span data-stu-id="0fd2a-264">See also</span></span>

- [<span data-ttu-id="0fd2a-265">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="0fd2a-265">CLR ETW Events</span></span>](clr-etw-events.md)
