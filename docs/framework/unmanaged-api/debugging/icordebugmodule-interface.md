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
ms.openlocfilehash: 971d6a6a2157c48dcb9105e9f523b1f077098479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129489"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="5dfa6-102">Интерфейс ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="5dfa6-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="5dfa6-103">Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="5dfa6-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5dfa6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5dfa6-104">Methods</span></span>  
  
|<span data-ttu-id="5dfa6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5dfa6-105">Method</span></span>|<span data-ttu-id="5dfa6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5dfa6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5dfa6-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5dfa6-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="5dfa6-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-108">Not implemented.</span></span>|  
|[<span data-ttu-id="5dfa6-109">Метод EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="5dfa6-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="5dfa6-110">Определяет, вызываются ли для этого модуля обратные вызовы [ICorDebugManagedCallback:: loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5dfa6-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="5dfa6-111">Метод EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="5dfa6-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="5dfa6-112">Определяет, будет ли JIT-компилятор сохранить отладочную информацию для методов в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="5dfa6-113">Метод GetAssembly</span><span class="sxs-lookup"><span data-stu-id="5dfa6-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="5dfa6-114">Возвращает содержащуюся сборку для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="5dfa6-115">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="5dfa6-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="5dfa6-116">Возвращает базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="5dfa6-117">Метод GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="5dfa6-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="5dfa6-118">Возвращает ICorDebugClass из метаданных.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="5dfa6-119">Метод GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="5dfa6-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="5dfa6-120">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-120">Deprecated.</span></span>|  
|[<span data-ttu-id="5dfa6-121">Метод GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="5dfa6-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="5dfa6-122">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-122">Not implemented.</span></span>|  
|[<span data-ttu-id="5dfa6-123">Метод GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="5dfa6-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="5dfa6-124">Возвращает функцию, заданную маркером метаданных.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="5dfa6-125">Метод GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="5dfa6-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="5dfa6-126">Возвращает объект значения для указанной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="5dfa6-127">Метод GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="5dfa6-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="5dfa6-128">Возвращает указатель интерфейса метаданных, который может использоваться для проверки метаданных модуля.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="5dfa6-129">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="5dfa6-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="5dfa6-130">Возвращает имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="5dfa6-131">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="5dfa6-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="5dfa6-132">Возвращает содержащий процесс для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="5dfa6-133">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="5dfa6-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="5dfa6-134">Возвращает размер модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="5dfa6-135">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="5dfa6-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="5dfa6-136">Возвращает маркер для записи таблицы для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="5dfa6-137">Метод IsDynamic</span><span class="sxs-lookup"><span data-stu-id="5dfa6-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="5dfa6-138">Указывает, является ли модуль динамическим.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="5dfa6-139">Метод IsInMemory</span><span class="sxs-lookup"><span data-stu-id="5dfa6-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="5dfa6-140">Указывает, существует ли этот модуль только в памяти.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dfa6-141">Заметки</span><span class="sxs-lookup"><span data-stu-id="5dfa6-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5dfa6-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5dfa6-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dfa6-143">Требования</span><span class="sxs-lookup"><span data-stu-id="5dfa6-143">Requirements</span></span>  
 <span data-ttu-id="5dfa6-144">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dfa6-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dfa6-145">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5dfa6-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5dfa6-146">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dfa6-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5dfa6-147">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dfa6-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dfa6-148">См. также</span><span class="sxs-lookup"><span data-stu-id="5dfa6-148">See also</span></span>

- [<span data-ttu-id="5dfa6-149">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5dfa6-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="5dfa6-150">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5dfa6-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
