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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fd8314c018653703a262c8c43e6113886c25047
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978687"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="00873-102">Интерфейс ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="00873-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="00873-103">Представляет общий модуль языка среды выполнения (CLR), исполняемого файла или библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="00873-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00873-104">Методы</span><span class="sxs-lookup"><span data-stu-id="00873-104">Methods</span></span>  
  
|<span data-ttu-id="00873-105">Метод</span><span class="sxs-lookup"><span data-stu-id="00873-105">Method</span></span>|<span data-ttu-id="00873-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="00873-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00873-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="00873-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="00873-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="00873-108">Not implemented.</span></span>|  
|[<span data-ttu-id="00873-109">Метод EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="00873-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="00873-110">Определяет, является ли [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) обратные вызовы, называются для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="00873-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="00873-111">Метод EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="00873-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="00873-112">Определяет, сохраняет ли компилятор just-in-time (JIT) сведения об отладке для методов в данном модуле.</span><span class="sxs-lookup"><span data-stu-id="00873-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="00873-113">Метод GetAssembly</span><span class="sxs-lookup"><span data-stu-id="00873-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="00873-114">Получает соответствующая сборка для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="00873-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="00873-115">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="00873-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="00873-116">Получает базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="00873-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="00873-117">Метод GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="00873-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="00873-118">Получает ICorDebugClass из метаданных.</span><span class="sxs-lookup"><span data-stu-id="00873-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="00873-119">Метод GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="00873-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="00873-120">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="00873-120">Deprecated.</span></span>|  
|[<span data-ttu-id="00873-121">Метод GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="00873-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="00873-122">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="00873-122">Not implemented.</span></span>|  
|[<span data-ttu-id="00873-123">Метод GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="00873-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="00873-124">Возвращает функцию, которое определяется токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="00873-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="00873-125">Метод GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="00873-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="00873-126">Возвращает объект значения для указанной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="00873-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="00873-127">Метод GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="00873-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="00873-128">Получает указатель на интерфейс метаданных, который может использоваться для просмотра метаданных для модуля.</span><span class="sxs-lookup"><span data-stu-id="00873-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="00873-129">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="00873-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="00873-130">Возвращает имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="00873-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="00873-131">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="00873-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="00873-132">Получает процесс, содержащий для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="00873-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="00873-133">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="00873-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="00873-134">Получает размер блока в байтах.</span><span class="sxs-lookup"><span data-stu-id="00873-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="00873-135">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="00873-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="00873-136">Получает токен для записи в таблице для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="00873-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="00873-137">Метод IsDynamic</span><span class="sxs-lookup"><span data-stu-id="00873-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="00873-138">Указывает, является ли динамический модуль.</span><span class="sxs-lookup"><span data-stu-id="00873-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="00873-139">Метод IsInMemory</span><span class="sxs-lookup"><span data-stu-id="00873-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="00873-140">Указывает, существует ли этот модуль только в памяти.</span><span class="sxs-lookup"><span data-stu-id="00873-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00873-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="00873-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00873-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="00873-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00873-143">Требования</span><span class="sxs-lookup"><span data-stu-id="00873-143">Requirements</span></span>  
 <span data-ttu-id="00873-144">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00873-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00873-145">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00873-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00873-146">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00873-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00873-147">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00873-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00873-148">См. также</span><span class="sxs-lookup"><span data-stu-id="00873-148">See also</span></span>
- [<span data-ttu-id="00873-149">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="00873-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="00873-150">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="00873-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
