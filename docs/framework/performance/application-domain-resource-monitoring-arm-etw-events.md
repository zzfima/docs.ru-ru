---
title: События отслеживания ресурсов домена приложения (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e1c2a38be6f2c15a118b35925570119b474f096
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040567"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="2bea9-102">События отслеживания ресурсов домена приложения (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="2bea9-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="2bea9-103">Эти события предоставляют подробные диагностические сведения о состоянии домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2bea9-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="2bea9-104">Эти события и функция отслеживания ресурсов домена приложения позволяют получить одни и те же сведения.</span><span class="sxs-lookup"><span data-stu-id="2bea9-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="2bea9-105">Событие ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="2bea9-105">ThreadCreated Event</span></span>

<span data-ttu-id="2bea9-106">Это событие также создается при использовании поставщика очистки как `ThreadDC` (при ключевом слове `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="2bea9-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="2bea9-107">Это единственное событие этой категории, создаваемое при использовании поставщика очистки.</span><span class="sxs-lookup"><span data-stu-id="2bea9-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="2bea9-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="2bea9-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="2bea9-109">Дополнительные сведения см. в разделе [Ключевые слова и уровни ETW среды CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2bea9-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="2bea9-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="2bea9-110">Keyword for raising the event</span></span>|<span data-ttu-id="2bea9-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="2bea9-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2bea9-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2bea9-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2bea9-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-113">Informational(4)</span></span>|
|<span data-ttu-id="2bea9-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2bea9-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2bea9-115">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-115">Informational(4)</span></span>|

<span data-ttu-id="2bea9-116">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="2bea9-116">The following table shows the event information:</span></span>

|<span data-ttu-id="2bea9-117">событие</span><span class="sxs-lookup"><span data-stu-id="2bea9-117">Event</span></span>|<span data-ttu-id="2bea9-118">Код события</span><span class="sxs-lookup"><span data-stu-id="2bea9-118">Event ID</span></span>|<span data-ttu-id="2bea9-119">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="2bea9-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="2bea9-120">85</span><span class="sxs-lookup"><span data-stu-id="2bea9-120">85</span></span>|<span data-ttu-id="2bea9-121">Поток создан для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2bea9-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="2bea9-122">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="2bea9-122">The following table shows the event data:</span></span>

|<span data-ttu-id="2bea9-123">Имя поля</span><span class="sxs-lookup"><span data-stu-id="2bea9-123">Field name</span></span>|<span data-ttu-id="2bea9-124">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2bea9-124">Data type</span></span>|<span data-ttu-id="2bea9-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2bea9-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2bea9-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2bea9-126">ThreadID</span></span>|<span data-ttu-id="2bea9-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-127">win:UInt64</span></span>|<span data-ttu-id="2bea9-128">Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="2bea9-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="2bea9-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2bea9-129">AppDomainID</span></span>|<span data-ttu-id="2bea9-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-130">win:UInt64</span></span>|<span data-ttu-id="2bea9-131">Идентификатор домена приложения, для которого сообщаются действия потоков.</span><span class="sxs-lookup"><span data-stu-id="2bea9-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="2bea9-132">Флаги</span><span class="sxs-lookup"><span data-stu-id="2bea9-132">Flags</span></span>|<span data-ttu-id="2bea9-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2bea9-133">win:UInt32</span></span>|<span data-ttu-id="2bea9-134">Флаги создания потока.</span><span class="sxs-lookup"><span data-stu-id="2bea9-134">Thread creation flags.</span></span>|
|<span data-ttu-id="2bea9-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="2bea9-135">ManagedThreadIndex</span></span>|<span data-ttu-id="2bea9-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2bea9-136">win:UInt32</span></span>|<span data-ttu-id="2bea9-137">Управляемый индекс созданного потока.</span><span class="sxs-lookup"><span data-stu-id="2bea9-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="2bea9-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="2bea9-138">OSThreadID</span></span>|<span data-ttu-id="2bea9-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2bea9-139">win:UInt32</span></span>|<span data-ttu-id="2bea9-140">Идентификатор операционной системы для созданного потока.</span><span class="sxs-lookup"><span data-stu-id="2bea9-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="2bea9-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2bea9-141">ClrInstanceID</span></span>|<span data-ttu-id="2bea9-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2bea9-142">win:UInt16</span></span>|<span data-ttu-id="2bea9-143">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2bea9-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="2bea9-144">Событие AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="2bea9-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="2bea9-145">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="2bea9-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2bea9-146">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="2bea9-146">Keyword for raising the event</span></span>|<span data-ttu-id="2bea9-147">Уровень</span><span class="sxs-lookup"><span data-stu-id="2bea9-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2bea9-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2bea9-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2bea9-149">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-149">Informational(4)</span></span>|

<span data-ttu-id="2bea9-150">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="2bea9-150">The following table shows the event information:</span></span>

|<span data-ttu-id="2bea9-151">событие</span><span class="sxs-lookup"><span data-stu-id="2bea9-151">Event</span></span>|<span data-ttu-id="2bea9-152">Код события</span><span class="sxs-lookup"><span data-stu-id="2bea9-152">Event ID</span></span>|<span data-ttu-id="2bea9-153">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="2bea9-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="2bea9-154">83</span><span class="sxs-lookup"><span data-stu-id="2bea9-154">83</span></span>|<span data-ttu-id="2bea9-155">В домене приложения выделяются каждые 4 МБ памяти (приблизительно).</span><span class="sxs-lookup"><span data-stu-id="2bea9-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="2bea9-156">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="2bea9-156">The following table shows the event data:</span></span>

|<span data-ttu-id="2bea9-157">Имя поля</span><span class="sxs-lookup"><span data-stu-id="2bea9-157">Field name</span></span>|<span data-ttu-id="2bea9-158">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2bea9-158">Data type</span></span>|<span data-ttu-id="2bea9-159">Описание</span><span class="sxs-lookup"><span data-stu-id="2bea9-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2bea9-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2bea9-160">AppDomainID</span></span>|<span data-ttu-id="2bea9-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-161">win:UInt64</span></span>|<span data-ttu-id="2bea9-162">Идентификатор домена приложения, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2bea9-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="2bea9-163">Allocated</span><span class="sxs-lookup"><span data-stu-id="2bea9-163">Allocated</span></span>|<span data-ttu-id="2bea9-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-164">win:UInt64</span></span>|<span data-ttu-id="2bea9-165">Общее число байтов, выделенных в этом домене приложения с момента его создания (объем свободной памяти не вычитается).</span><span class="sxs-lookup"><span data-stu-id="2bea9-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="2bea9-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2bea9-166">ClrInstanceID</span></span>|<span data-ttu-id="2bea9-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2bea9-167">win:UInt16</span></span>|<span data-ttu-id="2bea9-168">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2bea9-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="2bea9-169">Событие AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="2bea9-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="2bea9-170">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="2bea9-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2bea9-171">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="2bea9-171">Keyword for raising the event</span></span>|<span data-ttu-id="2bea9-172">Уровень</span><span class="sxs-lookup"><span data-stu-id="2bea9-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2bea9-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2bea9-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2bea9-174">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-174">Informational(4)</span></span>|

<span data-ttu-id="2bea9-175">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="2bea9-175">The following table shows the event information:</span></span>

|<span data-ttu-id="2bea9-176">событие</span><span class="sxs-lookup"><span data-stu-id="2bea9-176">Event</span></span>|<span data-ttu-id="2bea9-177">Код события</span><span class="sxs-lookup"><span data-stu-id="2bea9-177">Event ID</span></span>|<span data-ttu-id="2bea9-178">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="2bea9-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="2bea9-179">84</span><span class="sxs-lookup"><span data-stu-id="2bea9-179">84</span></span>|<span data-ttu-id="2bea9-180">Все сборки мусора закончены.</span><span class="sxs-lookup"><span data-stu-id="2bea9-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="2bea9-181">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="2bea9-181">The following table shows the event data:</span></span>

|<span data-ttu-id="2bea9-182">Имя поля</span><span class="sxs-lookup"><span data-stu-id="2bea9-182">Field name</span></span>|<span data-ttu-id="2bea9-183">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2bea9-183">Data type</span></span>|<span data-ttu-id="2bea9-184">Описание</span><span class="sxs-lookup"><span data-stu-id="2bea9-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2bea9-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2bea9-185">AppDomainID</span></span>|<span data-ttu-id="2bea9-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-186">win:UInt64</span></span>|<span data-ttu-id="2bea9-187">Идентификатор домена, для которого сообщаются сведения об использовании ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2bea9-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="2bea9-188">Survived</span><span class="sxs-lookup"><span data-stu-id="2bea9-188">Survived</span></span>|<span data-ttu-id="2bea9-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-189">win:UInt64</span></span>|<span data-ttu-id="2bea9-190">Количество байтов, оставшихся после последней сборки мусора и удерживаемых этим доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="2bea9-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="2bea9-191">Это число является точным и полным после полной сборки мусора, но может быть неполным после эфемерной сборки.</span><span class="sxs-lookup"><span data-stu-id="2bea9-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="2bea9-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="2bea9-192">ProcessSurvived</span></span>|<span data-ttu-id="2bea9-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-193">win:UInt64</span></span>|<span data-ttu-id="2bea9-194">Общее число байтов, сохранившихся после последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2bea9-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="2bea9-195">После полной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в управляемых кучах.</span><span class="sxs-lookup"><span data-stu-id="2bea9-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="2bea9-196">После эфемерной сборки мусора это число представляет количество байтов, сохраняющихся в активном состоянии в эфемерных поколениях.</span><span class="sxs-lookup"><span data-stu-id="2bea9-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="2bea9-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2bea9-197">ClrInstanceID</span></span>|<span data-ttu-id="2bea9-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2bea9-198">win:UInt16</span></span>|<span data-ttu-id="2bea9-199">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2bea9-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="2bea9-200">Событие ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="2bea9-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="2bea9-201">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="2bea9-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2bea9-202">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="2bea9-202">Keyword for raising the event</span></span>|<span data-ttu-id="2bea9-203">Уровень</span><span class="sxs-lookup"><span data-stu-id="2bea9-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2bea9-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2bea9-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2bea9-205">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-205">Informational(4)</span></span>|
|<span data-ttu-id="2bea9-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2bea9-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2bea9-207">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-207">Informational(4)</span></span>|

<span data-ttu-id="2bea9-208">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="2bea9-208">The following table shows the event information:</span></span>

|<span data-ttu-id="2bea9-209">событие</span><span class="sxs-lookup"><span data-stu-id="2bea9-209">Event</span></span>|<span data-ttu-id="2bea9-210">Код события</span><span class="sxs-lookup"><span data-stu-id="2bea9-210">Event ID</span></span>|<span data-ttu-id="2bea9-211">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="2bea9-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="2bea9-212">87</span><span class="sxs-lookup"><span data-stu-id="2bea9-212">87</span></span>|<span data-ttu-id="2bea9-213">Поток входит в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="2bea9-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="2bea9-214">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="2bea9-214">The following table shows the event data:</span></span>

|<span data-ttu-id="2bea9-215">Имя поля</span><span class="sxs-lookup"><span data-stu-id="2bea9-215">Field name</span></span>|<span data-ttu-id="2bea9-216">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2bea9-216">Data type</span></span>|<span data-ttu-id="2bea9-217">Описание</span><span class="sxs-lookup"><span data-stu-id="2bea9-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2bea9-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2bea9-218">ThreadID</span></span>|<span data-ttu-id="2bea9-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-219">win:UInt64</span></span>|<span data-ttu-id="2bea9-220">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="2bea9-220">The thread identifier.</span></span>|
|<span data-ttu-id="2bea9-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2bea9-221">AppDomainID</span></span>|<span data-ttu-id="2bea9-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-222">win:UInt64</span></span>|<span data-ttu-id="2bea9-223">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2bea9-223">The application domain identifier.</span></span>|
|<span data-ttu-id="2bea9-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2bea9-224">ClrInstanceID</span></span>|<span data-ttu-id="2bea9-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2bea9-225">win:UInt16</span></span>|<span data-ttu-id="2bea9-226">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2bea9-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="2bea9-227">Событие ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="2bea9-227">ThreadTerminated Event</span></span>

<span data-ttu-id="2bea9-228">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="2bea9-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="2bea9-229">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="2bea9-229">Keyword for raising the event</span></span>|<span data-ttu-id="2bea9-230">Уровень</span><span class="sxs-lookup"><span data-stu-id="2bea9-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2bea9-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="2bea9-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="2bea9-232">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-232">Informational(4)</span></span>|
|<span data-ttu-id="2bea9-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2bea9-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2bea9-234">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="2bea9-234">Informational(4)</span></span>|

<span data-ttu-id="2bea9-235">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="2bea9-235">The following table shows the event information:</span></span>

|<span data-ttu-id="2bea9-236">событие</span><span class="sxs-lookup"><span data-stu-id="2bea9-236">Event</span></span>|<span data-ttu-id="2bea9-237">Код события</span><span class="sxs-lookup"><span data-stu-id="2bea9-237">Event ID</span></span>|<span data-ttu-id="2bea9-238">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="2bea9-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="2bea9-239">86</span><span class="sxs-lookup"><span data-stu-id="2bea9-239">86</span></span>|<span data-ttu-id="2bea9-240">Поток завершается.</span><span class="sxs-lookup"><span data-stu-id="2bea9-240">A thread terminates.</span></span>|

<span data-ttu-id="2bea9-241">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="2bea9-241">The following table shows the event data:</span></span>

|<span data-ttu-id="2bea9-242">Имя поля</span><span class="sxs-lookup"><span data-stu-id="2bea9-242">Field name</span></span>|<span data-ttu-id="2bea9-243">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2bea9-243">Data type</span></span>|<span data-ttu-id="2bea9-244">Описание</span><span class="sxs-lookup"><span data-stu-id="2bea9-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="2bea9-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="2bea9-245">ThreadID</span></span>|<span data-ttu-id="2bea9-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-246">win:UInt64</span></span>|<span data-ttu-id="2bea9-247">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="2bea9-247">The thread identifier.</span></span>|
|<span data-ttu-id="2bea9-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="2bea9-248">AppDomainID</span></span>|<span data-ttu-id="2bea9-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2bea9-249">win:UInt64</span></span>|<span data-ttu-id="2bea9-250">Идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2bea9-250">The application domain identifier.</span></span>|
|<span data-ttu-id="2bea9-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2bea9-251">ClrInstanceID</span></span>|<span data-ttu-id="2bea9-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2bea9-252">win:UInt16</span></span>|<span data-ttu-id="2bea9-253">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2bea9-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2bea9-254">См. также</span><span class="sxs-lookup"><span data-stu-id="2bea9-254">See also</span></span>

- [<span data-ttu-id="2bea9-255">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="2bea9-255">CLR ETW Events</span></span>](clr-etw-events.md)
