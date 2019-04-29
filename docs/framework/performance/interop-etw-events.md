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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949309"
---
# <a name="interop-etw-events"></a><span data-ttu-id="74325-102">События взаимодействия (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="74325-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="74325-103">С помощью событий взаимодействия регистрируются сведения о создании заглушек и кэшировании MSIL.</span><span class="sxs-lookup"><span data-stu-id="74325-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="74325-104">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="74325-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="74325-105">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="74325-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
- [<span data-ttu-id="74325-106">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="74325-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="74325-107">Событие ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="74325-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="74325-108">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="74325-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="74325-109">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="74325-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="74325-110">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="74325-110">Keyword for raising the event</span></span>|<span data-ttu-id="74325-111">Уровень</span><span class="sxs-lookup"><span data-stu-id="74325-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="74325-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="74325-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="74325-113">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="74325-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="74325-114">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="74325-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="74325-115">событие</span><span class="sxs-lookup"><span data-stu-id="74325-115">Event</span></span>|<span data-ttu-id="74325-116">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="74325-116">Event ID</span></span>|<span data-ttu-id="74325-117">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="74325-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="74325-118">88</span><span class="sxs-lookup"><span data-stu-id="74325-118">88</span></span>|<span data-ttu-id="74325-119">Была создана заглушка языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="74325-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="74325-120">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="74325-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="74325-121">Имя поля</span><span class="sxs-lookup"><span data-stu-id="74325-121">Field name</span></span>|<span data-ttu-id="74325-122">Тип данных</span><span class="sxs-lookup"><span data-stu-id="74325-122">Data type</span></span>|<span data-ttu-id="74325-123">Описание</span><span class="sxs-lookup"><span data-stu-id="74325-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="74325-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="74325-124">ModuleID</span></span>|<span data-ttu-id="74325-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="74325-125">win:UInt16</span></span>|<span data-ttu-id="74325-126">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="74325-126">The module identifier.</span></span>|  
|<span data-ttu-id="74325-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="74325-127">StubMethodID</span></span>|<span data-ttu-id="74325-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="74325-128">win:UInt64</span></span>|<span data-ttu-id="74325-129">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="74325-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="74325-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="74325-130">StubFlags</span></span>|<span data-ttu-id="74325-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="74325-131">win:UInt64</span></span>|<span data-ttu-id="74325-132">Флаги для заглушки:</span><span class="sxs-lookup"><span data-stu-id="74325-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="74325-133">0x1 — обратное взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="74325-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="74325-134">0x2 — COM-взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="74325-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="74325-135">0x4 — заглушка, созданная программой NGen.exe;</span><span class="sxs-lookup"><span data-stu-id="74325-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="74325-136">0x8 — делегат;</span><span class="sxs-lookup"><span data-stu-id="74325-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="74325-137">0x10 — переменный аргумент;</span><span class="sxs-lookup"><span data-stu-id="74325-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="74325-138">0x20 — неуправляемый вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="74325-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="74325-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="74325-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="74325-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="74325-140">win:UInt32</span></span>|<span data-ttu-id="74325-141">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="74325-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="74325-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="74325-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-143">win:UnicodeString</span></span>|<span data-ttu-id="74325-144">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="74325-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="74325-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="74325-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-146">win:UnicodeString</span></span>|<span data-ttu-id="74325-147">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="74325-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="74325-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="74325-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-149">win:UnicodeString</span></span>|<span data-ttu-id="74325-150">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="74325-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="74325-151">NativeMethodSignature</span></span>|<span data-ttu-id="74325-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-152">win:UnicodeString</span></span>|<span data-ttu-id="74325-153">Сигнатура неуправляемого метода.</span><span class="sxs-lookup"><span data-stu-id="74325-153">The native method signature.</span></span>|  
|<span data-ttu-id="74325-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="74325-154">StubMethodSignature</span></span>|<span data-ttu-id="74325-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-155">win:UnicodeString</span></span>|<span data-ttu-id="74325-156">Сигнатура метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="74325-156">The stub method signature.</span></span>|  
|<span data-ttu-id="74325-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="74325-157">StubMethodILCode</span></span>|<span data-ttu-id="74325-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-158">win:UnicodeString</span></span>|<span data-ttu-id="74325-159">Код MSIL для метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="74325-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="74325-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="74325-160">ClrInstanceID</span></span>|<span data-ttu-id="74325-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="74325-161">win:UInt16</span></span>|<span data-ttu-id="74325-162">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="74325-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="74325-163">К началу</span><span class="sxs-lookup"><span data-stu-id="74325-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="74325-164">Событие ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="74325-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="74325-165">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="74325-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="74325-166">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="74325-166">Keyword for raising the event</span></span>|<span data-ttu-id="74325-167">Уровень</span><span class="sxs-lookup"><span data-stu-id="74325-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="74325-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="74325-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="74325-169">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="74325-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="74325-170">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="74325-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="74325-171">событие</span><span class="sxs-lookup"><span data-stu-id="74325-171">Event</span></span>|<span data-ttu-id="74325-172">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="74325-172">Event ID</span></span>|<span data-ttu-id="74325-173">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="74325-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="74325-174">89</span><span class="sxs-lookup"><span data-stu-id="74325-174">89</span></span>|<span data-ttu-id="74325-175">Обращение к кэшу MSIL.</span><span class="sxs-lookup"><span data-stu-id="74325-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="74325-176">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="74325-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="74325-177">Имя поля</span><span class="sxs-lookup"><span data-stu-id="74325-177">Field name</span></span>|<span data-ttu-id="74325-178">Тип данных</span><span class="sxs-lookup"><span data-stu-id="74325-178">Data type</span></span>|<span data-ttu-id="74325-179">Описание</span><span class="sxs-lookup"><span data-stu-id="74325-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="74325-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="74325-180">ModuleID</span></span>|<span data-ttu-id="74325-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="74325-181">win:UInt16</span></span>|<span data-ttu-id="74325-182">Идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="74325-182">The module identifier.</span></span>|  
|<span data-ttu-id="74325-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="74325-183">StubMethodID</span></span>|<span data-ttu-id="74325-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="74325-184">win:UInt64</span></span>|<span data-ttu-id="74325-185">Идентификатор метода-заглушки.</span><span class="sxs-lookup"><span data-stu-id="74325-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="74325-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="74325-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="74325-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="74325-187">win:UInt32</span></span>|<span data-ttu-id="74325-188">Токен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="74325-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="74325-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="74325-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-190">win:UnicodeString</span></span>|<span data-ttu-id="74325-191">Пространство имен управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="74325-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="74325-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="74325-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-193">win:UnicodeString</span></span>|<span data-ttu-id="74325-194">Имя управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="74325-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="74325-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="74325-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="74325-196">win:UnicodeString</span></span>|<span data-ttu-id="74325-197">Сигнатура управляемого метода взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="74325-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="74325-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="74325-198">ClrInstanceID</span></span>|<span data-ttu-id="74325-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="74325-199">win:UInt16</span></span>|<span data-ttu-id="74325-200">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="74325-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="74325-201">К началу</span><span class="sxs-lookup"><span data-stu-id="74325-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="74325-202">См. также</span><span class="sxs-lookup"><span data-stu-id="74325-202">See also</span></span>

- [<span data-ttu-id="74325-203">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="74325-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
