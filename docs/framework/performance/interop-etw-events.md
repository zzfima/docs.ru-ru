---
title: "События взаимодействия (трассировка событий Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5670eb910406626096f776d3b4192e2d58d7ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="6dca7-102">События взаимодействия (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="6dca7-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="6dca7-103">С помощью событий взаимодействия регистрируются сведения о создании заглушек и кэшировании MSIL.</span><span class="sxs-lookup"><span data-stu-id="6dca7-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="6dca7-104">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="6dca7-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="6dca7-105">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="6dca7-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="6dca7-106">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="6dca7-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="6dca7-107">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="6dca7-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="6dca7-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6dca7-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="6dca7-109">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="6dca7-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="6dca7-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6dca7-110">Keyword for raising the event</span></span>|<span data-ttu-id="6dca7-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="6dca7-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6dca7-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="6dca7-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="6dca7-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6dca7-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="6dca7-114">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6dca7-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6dca7-115">Событие</span><span class="sxs-lookup"><span data-stu-id="6dca7-115">Event</span></span>|<span data-ttu-id="6dca7-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6dca7-116">Event ID</span></span>|<span data-ttu-id="6dca7-117">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6dca7-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="6dca7-118">88</span><span class="sxs-lookup"><span data-stu-id="6dca7-118">88</span></span>|<span data-ttu-id="6dca7-119">Была создана заглушка языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="6dca7-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="6dca7-120">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6dca7-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6dca7-121">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6dca7-121">Field name</span></span>|<span data-ttu-id="6dca7-122">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6dca7-122">Data type</span></span>|<span data-ttu-id="6dca7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="6dca7-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6dca7-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="6dca7-124">ModuleID</span></span>|<span data-ttu-id="6dca7-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6dca7-125">win:UInt16</span></span>|<span data-ttu-id="6dca7-126">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="6dca7-126">The module identifier.</span></span>|  
|<span data-ttu-id="6dca7-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="6dca7-127">StubMethodID</span></span>|<span data-ttu-id="6dca7-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6dca7-128">win:UInt64</span></span>|<span data-ttu-id="6dca7-129">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="6dca7-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="6dca7-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="6dca7-130">StubFlags</span></span>|<span data-ttu-id="6dca7-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6dca7-131">win:UInt64</span></span>|<span data-ttu-id="6dca7-132">Флаги для заглушки:</span><span class="sxs-lookup"><span data-stu-id="6dca7-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="6dca7-133">0x1 — обратное взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="6dca7-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="6dca7-134">0x2 — COM-взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="6dca7-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="6dca7-135">0x4 — заглушка, созданная программой NGen.exe;</span><span class="sxs-lookup"><span data-stu-id="6dca7-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="6dca7-136">0x8 — делегат;</span><span class="sxs-lookup"><span data-stu-id="6dca7-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="6dca7-137">0x10 — переменный аргумент;</span><span class="sxs-lookup"><span data-stu-id="6dca7-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="6dca7-138">0x20 — неуправляемый вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="6dca7-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="6dca7-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="6dca7-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="6dca7-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6dca7-140">win:UInt32</span></span>|<span data-ttu-id="6dca7-141">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="6dca7-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="6dca7-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-143">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-144">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="6dca7-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="6dca7-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-146">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-147">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="6dca7-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="6dca7-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-149">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-150">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="6dca7-151">NativeMethodSignature</span></span>|<span data-ttu-id="6dca7-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-152">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-153">Сигнатура неуправляемого метода.</span><span class="sxs-lookup"><span data-stu-id="6dca7-153">The native method signature.</span></span>|  
|<span data-ttu-id="6dca7-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="6dca7-154">StubMethodSignature</span></span>|<span data-ttu-id="6dca7-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-155">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-156">Сигнатура метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="6dca7-156">The stub method signature.</span></span>|  
|<span data-ttu-id="6dca7-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="6dca7-157">StubMethodILCode</span></span>|<span data-ttu-id="6dca7-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-158">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-159">Код MSIL для метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="6dca7-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="6dca7-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6dca7-160">ClrInstanceID</span></span>|<span data-ttu-id="6dca7-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6dca7-161">win:UInt16</span></span>|<span data-ttu-id="6dca7-162">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6dca7-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6dca7-163">К началу</span><span class="sxs-lookup"><span data-stu-id="6dca7-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="6dca7-164">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="6dca7-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="6dca7-165">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6dca7-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6dca7-166">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6dca7-166">Keyword for raising the event</span></span>|<span data-ttu-id="6dca7-167">Уровень</span><span class="sxs-lookup"><span data-stu-id="6dca7-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6dca7-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="6dca7-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="6dca7-169">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6dca7-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="6dca7-170">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6dca7-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6dca7-171">Событие</span><span class="sxs-lookup"><span data-stu-id="6dca7-171">Event</span></span>|<span data-ttu-id="6dca7-172">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6dca7-172">Event ID</span></span>|<span data-ttu-id="6dca7-173">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6dca7-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="6dca7-174">89</span><span class="sxs-lookup"><span data-stu-id="6dca7-174">89</span></span>|<span data-ttu-id="6dca7-175">Обращение к кэшу MSIL.</span><span class="sxs-lookup"><span data-stu-id="6dca7-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="6dca7-176">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6dca7-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6dca7-177">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6dca7-177">Field name</span></span>|<span data-ttu-id="6dca7-178">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6dca7-178">Data type</span></span>|<span data-ttu-id="6dca7-179">Описание</span><span class="sxs-lookup"><span data-stu-id="6dca7-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6dca7-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="6dca7-180">ModuleID</span></span>|<span data-ttu-id="6dca7-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6dca7-181">win:UInt16</span></span>|<span data-ttu-id="6dca7-182">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="6dca7-182">The module identifier.</span></span>|  
|<span data-ttu-id="6dca7-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="6dca7-183">StubMethodID</span></span>|<span data-ttu-id="6dca7-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6dca7-184">win:UInt64</span></span>|<span data-ttu-id="6dca7-185">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="6dca7-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="6dca7-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="6dca7-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="6dca7-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6dca7-187">win:UInt32</span></span>|<span data-ttu-id="6dca7-188">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="6dca7-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="6dca7-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-190">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-191">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="6dca7-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="6dca7-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-193">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-194">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="6dca7-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="6dca7-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6dca7-196">win:UnicodeString</span></span>|<span data-ttu-id="6dca7-197">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6dca7-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="6dca7-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6dca7-198">ClrInstanceID</span></span>|<span data-ttu-id="6dca7-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6dca7-199">win:UInt16</span></span>|<span data-ttu-id="6dca7-200">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6dca7-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6dca7-201">К началу</span><span class="sxs-lookup"><span data-stu-id="6dca7-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="6dca7-202">См. также</span><span class="sxs-lookup"><span data-stu-id="6dca7-202">See Also</span></span>  
 [<span data-ttu-id="6dca7-203">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="6dca7-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
