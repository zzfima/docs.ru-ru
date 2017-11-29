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
ms.openlocfilehash: 55097e38161ea5c76f4e46584241344ec5a52cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="43636-102">События взаимодействия (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="43636-102">Interop ETW Events</span></span>
<span data-ttu-id="43636-103"><a name="top"></a> С помощью событий взаимодействия регистрируются сведения о создании заглушек и кэшировании MSIL.</span><span class="sxs-lookup"><span data-stu-id="43636-103"><a name="top"></a> Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="43636-104">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="43636-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="43636-105">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="43636-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="43636-106">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="43636-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="43636-107">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="43636-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="43636-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="43636-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="43636-109">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="43636-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="43636-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="43636-110">Keyword for raising the event</span></span>|<span data-ttu-id="43636-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="43636-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="43636-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="43636-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="43636-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="43636-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="43636-114">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="43636-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="43636-115">Событие</span><span class="sxs-lookup"><span data-stu-id="43636-115">Event</span></span>|<span data-ttu-id="43636-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="43636-116">Event ID</span></span>|<span data-ttu-id="43636-117">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="43636-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="43636-118">88</span><span class="sxs-lookup"><span data-stu-id="43636-118">88</span></span>|<span data-ttu-id="43636-119">Была создана заглушка языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="43636-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="43636-120">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="43636-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="43636-121">Имя поля</span><span class="sxs-lookup"><span data-stu-id="43636-121">Field name</span></span>|<span data-ttu-id="43636-122">Тип данных</span><span class="sxs-lookup"><span data-stu-id="43636-122">Data type</span></span>|<span data-ttu-id="43636-123">Описание</span><span class="sxs-lookup"><span data-stu-id="43636-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="43636-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="43636-124">ModuleID</span></span>|<span data-ttu-id="43636-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="43636-125">win:UInt16</span></span>|<span data-ttu-id="43636-126">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="43636-126">The module identifier.</span></span>|  
|<span data-ttu-id="43636-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="43636-127">StubMethodID</span></span>|<span data-ttu-id="43636-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="43636-128">win:UInt64</span></span>|<span data-ttu-id="43636-129">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="43636-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="43636-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="43636-130">StubFlags</span></span>|<span data-ttu-id="43636-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="43636-131">win:UInt64</span></span>|<span data-ttu-id="43636-132">Флаги для заглушки:</span><span class="sxs-lookup"><span data-stu-id="43636-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="43636-133">0x1 — обратное взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="43636-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="43636-134">0x2 — COM-взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="43636-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="43636-135">0x4 — заглушка, созданная программой NGen.exe;</span><span class="sxs-lookup"><span data-stu-id="43636-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="43636-136">0x8 — делегат;</span><span class="sxs-lookup"><span data-stu-id="43636-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="43636-137">0x10 — переменный аргумент;</span><span class="sxs-lookup"><span data-stu-id="43636-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="43636-138">0x20 — неуправляемый вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="43636-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="43636-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="43636-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="43636-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="43636-140">win:UInt32</span></span>|<span data-ttu-id="43636-141">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="43636-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="43636-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="43636-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-143">win:UnicodeString</span></span>|<span data-ttu-id="43636-144">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="43636-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="43636-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="43636-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-146">win:UnicodeString</span></span>|<span data-ttu-id="43636-147">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="43636-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="43636-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="43636-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-149">win:UnicodeString</span></span>|<span data-ttu-id="43636-150">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="43636-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="43636-151">NativeMethodSignature</span></span>|<span data-ttu-id="43636-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-152">win:UnicodeString</span></span>|<span data-ttu-id="43636-153">Сигнатура неуправляемого метода.</span><span class="sxs-lookup"><span data-stu-id="43636-153">The native method signature.</span></span>|  
|<span data-ttu-id="43636-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="43636-154">StubMethodSignature</span></span>|<span data-ttu-id="43636-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-155">win:UnicodeString</span></span>|<span data-ttu-id="43636-156">Сигнатура метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="43636-156">The stub method signature.</span></span>|  
|<span data-ttu-id="43636-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="43636-157">StubMethodILCode</span></span>|<span data-ttu-id="43636-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-158">win:UnicodeString</span></span>|<span data-ttu-id="43636-159">Код MSIL для метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="43636-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="43636-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="43636-160">ClrInstanceID</span></span>|<span data-ttu-id="43636-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="43636-161">win:UInt16</span></span>|<span data-ttu-id="43636-162">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="43636-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="43636-163">К началу</span><span class="sxs-lookup"><span data-stu-id="43636-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="43636-164">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="43636-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="43636-165">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="43636-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="43636-166">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="43636-166">Keyword for raising the event</span></span>|<span data-ttu-id="43636-167">Уровень</span><span class="sxs-lookup"><span data-stu-id="43636-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="43636-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="43636-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="43636-169">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="43636-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="43636-170">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="43636-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="43636-171">Событие</span><span class="sxs-lookup"><span data-stu-id="43636-171">Event</span></span>|<span data-ttu-id="43636-172">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="43636-172">Event ID</span></span>|<span data-ttu-id="43636-173">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="43636-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="43636-174">89</span><span class="sxs-lookup"><span data-stu-id="43636-174">89</span></span>|<span data-ttu-id="43636-175">Обращение к кэшу MSIL.</span><span class="sxs-lookup"><span data-stu-id="43636-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="43636-176">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="43636-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="43636-177">Имя поля</span><span class="sxs-lookup"><span data-stu-id="43636-177">Field name</span></span>|<span data-ttu-id="43636-178">Тип данных</span><span class="sxs-lookup"><span data-stu-id="43636-178">Data type</span></span>|<span data-ttu-id="43636-179">Описание</span><span class="sxs-lookup"><span data-stu-id="43636-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="43636-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="43636-180">ModuleID</span></span>|<span data-ttu-id="43636-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="43636-181">win:UInt16</span></span>|<span data-ttu-id="43636-182">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="43636-182">The module identifier.</span></span>|  
|<span data-ttu-id="43636-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="43636-183">StubMethodID</span></span>|<span data-ttu-id="43636-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="43636-184">win:UInt64</span></span>|<span data-ttu-id="43636-185">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="43636-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="43636-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="43636-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="43636-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="43636-187">win:UInt32</span></span>|<span data-ttu-id="43636-188">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="43636-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="43636-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="43636-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-190">win:UnicodeString</span></span>|<span data-ttu-id="43636-191">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="43636-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="43636-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="43636-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-193">win:UnicodeString</span></span>|<span data-ttu-id="43636-194">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="43636-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="43636-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="43636-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="43636-196">win:UnicodeString</span></span>|<span data-ttu-id="43636-197">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="43636-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="43636-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="43636-198">ClrInstanceID</span></span>|<span data-ttu-id="43636-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="43636-199">win:UInt16</span></span>|<span data-ttu-id="43636-200">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="43636-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="43636-201">К началу</span><span class="sxs-lookup"><span data-stu-id="43636-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="43636-202">См. также</span><span class="sxs-lookup"><span data-stu-id="43636-202">See Also</span></span>  
 [<span data-ttu-id="43636-203">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="43636-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
