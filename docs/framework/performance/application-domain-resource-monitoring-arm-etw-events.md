---
title: События отслеживания ресурсов домена приложения (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: 0e453b2bafffd9e07a1bdddd97282c5b97f5483d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716213"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="83993-102">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="83993-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="83993-103">Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83993-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="83993-104">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="83993-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="83993-105">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="83993-105">ThreadCreated Event</span></span>

<span data-ttu-id="83993-106">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="83993-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="83993-107">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="83993-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="83993-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="83993-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="83993-109">Дополнительные сведения см. в разделе [Ключевые слова и уровни ETW среды CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="83993-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="83993-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="83993-110">Keyword for raising the event</span></span>|<span data-ttu-id="83993-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="83993-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="83993-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="83993-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="83993-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-113">Informational(4)</span></span>|
|<span data-ttu-id="83993-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="83993-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="83993-115">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-115">Informational(4)</span></span>|

<span data-ttu-id="83993-116">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="83993-116">The following table shows the event information:</span></span>

|<span data-ttu-id="83993-117">Event</span><span class="sxs-lookup"><span data-stu-id="83993-117">Event</span></span>|<span data-ttu-id="83993-118">Код события</span><span class="sxs-lookup"><span data-stu-id="83993-118">Event ID</span></span>|<span data-ttu-id="83993-119">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="83993-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="83993-120">85</span><span class="sxs-lookup"><span data-stu-id="83993-120">85</span></span>|<span data-ttu-id="83993-121">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83993-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="83993-122">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="83993-122">The following table shows the event data:</span></span>

|<span data-ttu-id="83993-123">Имя поля</span><span class="sxs-lookup"><span data-stu-id="83993-123">Field name</span></span>|<span data-ttu-id="83993-124">Тип данных</span><span class="sxs-lookup"><span data-stu-id="83993-124">Data type</span></span>|<span data-ttu-id="83993-125">Описание</span><span class="sxs-lookup"><span data-stu-id="83993-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="83993-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="83993-126">ThreadID</span></span>|<span data-ttu-id="83993-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-127">win:UInt64</span></span>|<span data-ttu-id="83993-128">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="83993-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="83993-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="83993-129">AppDomainID</span></span>|<span data-ttu-id="83993-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-130">win:UInt64</span></span>|<span data-ttu-id="83993-131">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="83993-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="83993-132">Флаги</span><span class="sxs-lookup"><span data-stu-id="83993-132">Flags</span></span>|<span data-ttu-id="83993-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="83993-133">win:UInt32</span></span>|<span data-ttu-id="83993-134">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="83993-134">Thread creation flags.</span></span>|
|<span data-ttu-id="83993-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="83993-135">ManagedThreadIndex</span></span>|<span data-ttu-id="83993-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="83993-136">win:UInt32</span></span>|<span data-ttu-id="83993-137">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="83993-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="83993-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="83993-138">OSThreadID</span></span>|<span data-ttu-id="83993-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="83993-139">win:UInt32</span></span>|<span data-ttu-id="83993-140">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="83993-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="83993-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="83993-141">ClrInstanceID</span></span>|<span data-ttu-id="83993-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="83993-142">win:UInt16</span></span>|<span data-ttu-id="83993-143">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="83993-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="83993-144">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="83993-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="83993-145">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="83993-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="83993-146">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="83993-146">Keyword for raising the event</span></span>|<span data-ttu-id="83993-147">Уровень</span><span class="sxs-lookup"><span data-stu-id="83993-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="83993-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="83993-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="83993-149">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-149">Informational(4)</span></span>|

<span data-ttu-id="83993-150">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="83993-150">The following table shows the event information:</span></span>

|<span data-ttu-id="83993-151">Event</span><span class="sxs-lookup"><span data-stu-id="83993-151">Event</span></span>|<span data-ttu-id="83993-152">Код события</span><span class="sxs-lookup"><span data-stu-id="83993-152">Event ID</span></span>|<span data-ttu-id="83993-153">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="83993-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="83993-154">83</span><span class="sxs-lookup"><span data-stu-id="83993-154">83</span></span>|<span data-ttu-id="83993-155">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="83993-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="83993-156">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="83993-156">The following table shows the event data:</span></span>

|<span data-ttu-id="83993-157">Имя поля</span><span class="sxs-lookup"><span data-stu-id="83993-157">Field name</span></span>|<span data-ttu-id="83993-158">Тип данных</span><span class="sxs-lookup"><span data-stu-id="83993-158">Data type</span></span>|<span data-ttu-id="83993-159">Описание</span><span class="sxs-lookup"><span data-stu-id="83993-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="83993-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="83993-160">AppDomainID</span></span>|<span data-ttu-id="83993-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-161">win:UInt64</span></span>|<span data-ttu-id="83993-162">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="83993-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="83993-163">Allocated</span><span class="sxs-lookup"><span data-stu-id="83993-163">Allocated</span></span>|<span data-ttu-id="83993-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-164">win:UInt64</span></span>|<span data-ttu-id="83993-165">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="83993-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="83993-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="83993-166">ClrInstanceID</span></span>|<span data-ttu-id="83993-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="83993-167">win:UInt16</span></span>|<span data-ttu-id="83993-168">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="83993-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="83993-169">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="83993-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="83993-170">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="83993-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="83993-171">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="83993-171">Keyword for raising the event</span></span>|<span data-ttu-id="83993-172">Уровень</span><span class="sxs-lookup"><span data-stu-id="83993-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="83993-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="83993-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="83993-174">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-174">Informational(4)</span></span>|

<span data-ttu-id="83993-175">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="83993-175">The following table shows the event information:</span></span>

|<span data-ttu-id="83993-176">Event</span><span class="sxs-lookup"><span data-stu-id="83993-176">Event</span></span>|<span data-ttu-id="83993-177">Код события</span><span class="sxs-lookup"><span data-stu-id="83993-177">Event ID</span></span>|<span data-ttu-id="83993-178">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="83993-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="83993-179">84</span><span class="sxs-lookup"><span data-stu-id="83993-179">84</span></span>|<span data-ttu-id="83993-180">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="83993-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="83993-181">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="83993-181">The following table shows the event data:</span></span>

|<span data-ttu-id="83993-182">Имя поля</span><span class="sxs-lookup"><span data-stu-id="83993-182">Field name</span></span>|<span data-ttu-id="83993-183">Тип данных</span><span class="sxs-lookup"><span data-stu-id="83993-183">Data type</span></span>|<span data-ttu-id="83993-184">Описание</span><span class="sxs-lookup"><span data-stu-id="83993-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="83993-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="83993-185">AppDomainID</span></span>|<span data-ttu-id="83993-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-186">win:UInt64</span></span>|<span data-ttu-id="83993-187">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="83993-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="83993-188">Survived</span><span class="sxs-lookup"><span data-stu-id="83993-188">Survived</span></span>|<span data-ttu-id="83993-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-189">win:UInt64</span></span>|<span data-ttu-id="83993-190">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="83993-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="83993-191">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="83993-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="83993-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="83993-192">ProcessSurvived</span></span>|<span data-ttu-id="83993-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-193">win:UInt64</span></span>|<span data-ttu-id="83993-194">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="83993-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="83993-195">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="83993-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="83993-196">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="83993-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="83993-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="83993-197">ClrInstanceID</span></span>|<span data-ttu-id="83993-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="83993-198">win:UInt16</span></span>|<span data-ttu-id="83993-199">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="83993-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="83993-200">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="83993-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="83993-201">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="83993-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="83993-202">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="83993-202">Keyword for raising the event</span></span>|<span data-ttu-id="83993-203">Уровень</span><span class="sxs-lookup"><span data-stu-id="83993-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="83993-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="83993-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="83993-205">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-205">Informational(4)</span></span>|
|<span data-ttu-id="83993-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="83993-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="83993-207">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-207">Informational(4)</span></span>|

<span data-ttu-id="83993-208">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="83993-208">The following table shows the event information:</span></span>

|<span data-ttu-id="83993-209">Event</span><span class="sxs-lookup"><span data-stu-id="83993-209">Event</span></span>|<span data-ttu-id="83993-210">Код события</span><span class="sxs-lookup"><span data-stu-id="83993-210">Event ID</span></span>|<span data-ttu-id="83993-211">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="83993-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="83993-212">87</span><span class="sxs-lookup"><span data-stu-id="83993-212">87</span></span>|<span data-ttu-id="83993-213">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="83993-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="83993-214">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="83993-214">The following table shows the event data:</span></span>

|<span data-ttu-id="83993-215">Имя поля</span><span class="sxs-lookup"><span data-stu-id="83993-215">Field name</span></span>|<span data-ttu-id="83993-216">Тип данных</span><span class="sxs-lookup"><span data-stu-id="83993-216">Data type</span></span>|<span data-ttu-id="83993-217">Описание</span><span class="sxs-lookup"><span data-stu-id="83993-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="83993-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="83993-218">ThreadID</span></span>|<span data-ttu-id="83993-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-219">win:UInt64</span></span>|<span data-ttu-id="83993-220">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="83993-220">The thread identifier.</span></span>|
|<span data-ttu-id="83993-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="83993-221">AppDomainID</span></span>|<span data-ttu-id="83993-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-222">win:UInt64</span></span>|<span data-ttu-id="83993-223">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83993-223">The application domain identifier.</span></span>|
|<span data-ttu-id="83993-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="83993-224">ClrInstanceID</span></span>|<span data-ttu-id="83993-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="83993-225">win:UInt16</span></span>|<span data-ttu-id="83993-226">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="83993-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="83993-227">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="83993-227">ThreadTerminated Event</span></span>

<span data-ttu-id="83993-228">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="83993-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="83993-229">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="83993-229">Keyword for raising the event</span></span>|<span data-ttu-id="83993-230">Уровень</span><span class="sxs-lookup"><span data-stu-id="83993-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="83993-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="83993-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="83993-232">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-232">Informational(4)</span></span>|
|<span data-ttu-id="83993-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="83993-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="83993-234">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="83993-234">Informational(4)</span></span>|

<span data-ttu-id="83993-235">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="83993-235">The following table shows the event information:</span></span>

|<span data-ttu-id="83993-236">Event</span><span class="sxs-lookup"><span data-stu-id="83993-236">Event</span></span>|<span data-ttu-id="83993-237">Код события</span><span class="sxs-lookup"><span data-stu-id="83993-237">Event ID</span></span>|<span data-ttu-id="83993-238">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="83993-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="83993-239">86</span><span class="sxs-lookup"><span data-stu-id="83993-239">86</span></span>|<span data-ttu-id="83993-240">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="83993-240">A thread terminates.</span></span>|

<span data-ttu-id="83993-241">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="83993-241">The following table shows the event data:</span></span>

|<span data-ttu-id="83993-242">Имя поля</span><span class="sxs-lookup"><span data-stu-id="83993-242">Field name</span></span>|<span data-ttu-id="83993-243">Тип данных</span><span class="sxs-lookup"><span data-stu-id="83993-243">Data type</span></span>|<span data-ttu-id="83993-244">Описание</span><span class="sxs-lookup"><span data-stu-id="83993-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="83993-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="83993-245">ThreadID</span></span>|<span data-ttu-id="83993-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-246">win:UInt64</span></span>|<span data-ttu-id="83993-247">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="83993-247">The thread identifier.</span></span>|
|<span data-ttu-id="83993-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="83993-248">AppDomainID</span></span>|<span data-ttu-id="83993-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="83993-249">win:UInt64</span></span>|<span data-ttu-id="83993-250">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="83993-250">The application domain identifier.</span></span>|
|<span data-ttu-id="83993-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="83993-251">ClrInstanceID</span></span>|<span data-ttu-id="83993-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="83993-252">win:UInt16</span></span>|<span data-ttu-id="83993-253">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="83993-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="83993-254">См. также:</span><span class="sxs-lookup"><span data-stu-id="83993-254">See also</span></span>

- [<span data-ttu-id="83993-255">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="83993-255">CLR ETW Events</span></span>](clr-etw-events.md)
