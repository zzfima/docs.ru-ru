---
title: Интерфейс ICorDebugModule
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
ms.openlocfilehash: c573e6b768aee1e8b681dcf2e828dc24d409025b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793017"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="700ee-102">Интерфейс ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="700ee-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="700ee-103">Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="700ee-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="700ee-104">Методы</span><span class="sxs-lookup"><span data-stu-id="700ee-104">Methods</span></span>  
  
|<span data-ttu-id="700ee-105">Метод</span><span class="sxs-lookup"><span data-stu-id="700ee-105">Method</span></span>|<span data-ttu-id="700ee-106">Описание</span><span class="sxs-lookup"><span data-stu-id="700ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="700ee-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="700ee-107">CreateBreakpoint Method</span></span>](icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="700ee-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="700ee-108">Not implemented.</span></span>|  
|[<span data-ttu-id="700ee-109">Метод EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="700ee-109">EnableClassLoadCallbacks Method</span></span>](icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="700ee-110">Определяет, вызываются ли для этого модуля обратные вызовы [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](icordebugmanagedcallback-unloadclass-method.md) .</span><span class="sxs-lookup"><span data-stu-id="700ee-110">Determines whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="700ee-111">Метод EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="700ee-111">EnableJITDebugging Method</span></span>](icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="700ee-112">Определяет, будет ли JIT-компилятор сохранить отладочную информацию для методов в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="700ee-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="700ee-113">Метод GetAssembly</span><span class="sxs-lookup"><span data-stu-id="700ee-113">GetAssembly Method</span></span>](icordebugmodule-getassembly-method.md)|<span data-ttu-id="700ee-114">Возвращает содержащуюся сборку для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="700ee-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="700ee-115">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="700ee-115">GetBaseAddress Method</span></span>](icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="700ee-116">Возвращает базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="700ee-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="700ee-117">Метод GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="700ee-117">GetClassFromToken Method</span></span>](icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="700ee-118">Возвращает ICorDebugClass из метаданных.</span><span class="sxs-lookup"><span data-stu-id="700ee-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="700ee-119">Метод GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="700ee-119">GetEditAndContinueSnapshot Method</span></span>](icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="700ee-120">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="700ee-120">Deprecated.</span></span>|  
|[<span data-ttu-id="700ee-121">Метод GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="700ee-121">GetFunctionFromRVA Method</span></span>](icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="700ee-122">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="700ee-122">Not implemented.</span></span>|  
|[<span data-ttu-id="700ee-123">Метод GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="700ee-123">GetFunctionFromToken Method</span></span>](icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="700ee-124">Возвращает функцию, заданную маркером метаданных.</span><span class="sxs-lookup"><span data-stu-id="700ee-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="700ee-125">Метод GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="700ee-125">GetGlobalVariableValue Method</span></span>](icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="700ee-126">Возвращает объект значения для указанной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="700ee-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="700ee-127">Метод GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="700ee-127">GetMetaDataInterface Method</span></span>](icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="700ee-128">Возвращает указатель интерфейса метаданных, который может использоваться для проверки метаданных модуля.</span><span class="sxs-lookup"><span data-stu-id="700ee-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="700ee-129">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="700ee-129">GetName Method</span></span>](icordebugmodule-getname-method.md)|<span data-ttu-id="700ee-130">Возвращает имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="700ee-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="700ee-131">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="700ee-131">GetProcess Method</span></span>](icordebugmodule-getprocess-method.md)|<span data-ttu-id="700ee-132">Возвращает содержащий процесс для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="700ee-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="700ee-133">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="700ee-133">GetSize Method</span></span>](icordebugmodule-getsize-method.md)|<span data-ttu-id="700ee-134">Возвращает размер модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="700ee-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="700ee-135">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="700ee-135">GetToken Method</span></span>](icordebugmodule-gettoken-method.md)|<span data-ttu-id="700ee-136">Возвращает маркер для записи таблицы для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="700ee-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="700ee-137">Метод IsDynamic</span><span class="sxs-lookup"><span data-stu-id="700ee-137">IsDynamic Method</span></span>](icordebugmodule-isdynamic-method.md)|<span data-ttu-id="700ee-138">Указывает, является ли модуль динамическим.</span><span class="sxs-lookup"><span data-stu-id="700ee-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="700ee-139">Метод IsInMemory</span><span class="sxs-lookup"><span data-stu-id="700ee-139">IsInMemory Method</span></span>](icordebugmodule-isinmemory-method.md)|<span data-ttu-id="700ee-140">Указывает, существует ли этот модуль только в памяти.</span><span class="sxs-lookup"><span data-stu-id="700ee-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="700ee-141">Заметки</span><span class="sxs-lookup"><span data-stu-id="700ee-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="700ee-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="700ee-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="700ee-143">Требования</span><span class="sxs-lookup"><span data-stu-id="700ee-143">Requirements</span></span>  
 <span data-ttu-id="700ee-144">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="700ee-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="700ee-145">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="700ee-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="700ee-146">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="700ee-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="700ee-147">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="700ee-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700ee-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="700ee-148">See also</span></span>

- [<span data-ttu-id="700ee-149">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="700ee-149">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="700ee-150">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="700ee-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
