---
title: События взаимодействия (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09b2848619256a255cc27f0268d46e5e6db8cbe4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083612"
---
# <a name="interop-etw-events"></a><span data-ttu-id="9d6d8-102">События взаимодействия (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="9d6d8-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="9d6d8-103">С помощью событий взаимодействия регистрируются сведения о создании заглушек и кэшировании MSIL.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="9d6d8-104">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="9d6d8-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="9d6d8-105">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="9d6d8-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="9d6d8-106">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="9d6d8-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="9d6d8-107">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="9d6d8-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="9d6d8-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="9d6d8-109">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="9d6d8-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="9d6d8-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="9d6d8-110">Keyword for raising the event</span></span>|<span data-ttu-id="9d6d8-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="9d6d8-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="9d6d8-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="9d6d8-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="9d6d8-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="9d6d8-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="9d6d8-114">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="9d6d8-115">событие</span><span class="sxs-lookup"><span data-stu-id="9d6d8-115">Event</span></span>|<span data-ttu-id="9d6d8-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="9d6d8-116">Event ID</span></span>|<span data-ttu-id="9d6d8-117">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="9d6d8-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="9d6d8-118">88</span><span class="sxs-lookup"><span data-stu-id="9d6d8-118">88</span></span>|<span data-ttu-id="9d6d8-119">Была создана заглушка языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="9d6d8-120">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="9d6d8-121">Имя поля</span><span class="sxs-lookup"><span data-stu-id="9d6d8-121">Field name</span></span>|<span data-ttu-id="9d6d8-122">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9d6d8-122">Data type</span></span>|<span data-ttu-id="9d6d8-123">Описание</span><span class="sxs-lookup"><span data-stu-id="9d6d8-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="9d6d8-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="9d6d8-124">ModuleID</span></span>|<span data-ttu-id="9d6d8-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9d6d8-125">win:UInt16</span></span>|<span data-ttu-id="9d6d8-126">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-126">The module identifier.</span></span>|  
|<span data-ttu-id="9d6d8-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="9d6d8-127">StubMethodID</span></span>|<span data-ttu-id="9d6d8-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9d6d8-128">win:UInt64</span></span>|<span data-ttu-id="9d6d8-129">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="9d6d8-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="9d6d8-130">StubFlags</span></span>|<span data-ttu-id="9d6d8-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9d6d8-131">win:UInt64</span></span>|<span data-ttu-id="9d6d8-132">Флаги для заглушки:</span><span class="sxs-lookup"><span data-stu-id="9d6d8-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="9d6d8-133">0x1 — обратное взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="9d6d8-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="9d6d8-134">0x2 — COM-взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="9d6d8-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="9d6d8-135">0x4 — заглушка, созданная программой NGen.exe;</span><span class="sxs-lookup"><span data-stu-id="9d6d8-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="9d6d8-136">0x8 — делегат;</span><span class="sxs-lookup"><span data-stu-id="9d6d8-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="9d6d8-137">0x10 — переменный аргумент;</span><span class="sxs-lookup"><span data-stu-id="9d6d8-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="9d6d8-138">0x20 — неуправляемый вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="9d6d8-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="9d6d8-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="9d6d8-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9d6d8-140">win:UInt32</span></span>|<span data-ttu-id="9d6d8-141">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="9d6d8-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="9d6d8-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-143">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-144">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="9d6d8-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="9d6d8-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-146">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-147">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="9d6d8-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="9d6d8-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-149">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-150">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="9d6d8-151">NativeMethodSignature</span></span>|<span data-ttu-id="9d6d8-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-152">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-153">Сигнатура неуправляемого метода.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-153">The native method signature.</span></span>|  
|<span data-ttu-id="9d6d8-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="9d6d8-154">StubMethodSignature</span></span>|<span data-ttu-id="9d6d8-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-155">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-156">Сигнатура метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-156">The stub method signature.</span></span>|  
|<span data-ttu-id="9d6d8-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="9d6d8-157">StubMethodILCode</span></span>|<span data-ttu-id="9d6d8-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-158">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-159">Код MSIL для метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="9d6d8-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9d6d8-160">ClrInstanceID</span></span>|<span data-ttu-id="9d6d8-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9d6d8-161">win:UInt16</span></span>|<span data-ttu-id="9d6d8-162">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="9d6d8-163">К началу</span><span class="sxs-lookup"><span data-stu-id="9d6d8-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="9d6d8-164">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="9d6d8-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="9d6d8-165">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="9d6d8-166">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="9d6d8-166">Keyword for raising the event</span></span>|<span data-ttu-id="9d6d8-167">Уровень</span><span class="sxs-lookup"><span data-stu-id="9d6d8-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="9d6d8-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="9d6d8-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="9d6d8-169">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="9d6d8-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="9d6d8-170">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="9d6d8-171">событие</span><span class="sxs-lookup"><span data-stu-id="9d6d8-171">Event</span></span>|<span data-ttu-id="9d6d8-172">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="9d6d8-172">Event ID</span></span>|<span data-ttu-id="9d6d8-173">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="9d6d8-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="9d6d8-174">89</span><span class="sxs-lookup"><span data-stu-id="9d6d8-174">89</span></span>|<span data-ttu-id="9d6d8-175">Обращение к кэшу MSIL.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="9d6d8-176">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="9d6d8-177">Имя поля</span><span class="sxs-lookup"><span data-stu-id="9d6d8-177">Field name</span></span>|<span data-ttu-id="9d6d8-178">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9d6d8-178">Data type</span></span>|<span data-ttu-id="9d6d8-179">Описание</span><span class="sxs-lookup"><span data-stu-id="9d6d8-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="9d6d8-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="9d6d8-180">ModuleID</span></span>|<span data-ttu-id="9d6d8-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9d6d8-181">win:UInt16</span></span>|<span data-ttu-id="9d6d8-182">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-182">The module identifier.</span></span>|  
|<span data-ttu-id="9d6d8-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="9d6d8-183">StubMethodID</span></span>|<span data-ttu-id="9d6d8-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="9d6d8-184">win:UInt64</span></span>|<span data-ttu-id="9d6d8-185">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="9d6d8-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="9d6d8-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="9d6d8-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9d6d8-187">win:UInt32</span></span>|<span data-ttu-id="9d6d8-188">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="9d6d8-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="9d6d8-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-190">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-191">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="9d6d8-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="9d6d8-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-193">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-194">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="9d6d8-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="9d6d8-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9d6d8-196">win:UnicodeString</span></span>|<span data-ttu-id="9d6d8-197">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="9d6d8-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9d6d8-198">ClrInstanceID</span></span>|<span data-ttu-id="9d6d8-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9d6d8-199">win:UInt16</span></span>|<span data-ttu-id="9d6d8-200">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9d6d8-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="9d6d8-201">К началу</span><span class="sxs-lookup"><span data-stu-id="9d6d8-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="9d6d8-202">См. также</span><span class="sxs-lookup"><span data-stu-id="9d6d8-202">See also</span></span>

- [<span data-ttu-id="9d6d8-203">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="9d6d8-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
