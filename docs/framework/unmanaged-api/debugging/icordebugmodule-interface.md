---
title: "ICorDebugModule интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59c24d8305e71aac01843155b86fb54fb1e1263d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule-interface1"></a><span data-ttu-id="cdc86-102">ICorDebugModule интерфейс1</span><span class="sxs-lookup"><span data-stu-id="cdc86-102">ICorDebugModule Interface1</span></span>
<span data-ttu-id="cdc86-103">Представляет общий модуль среды выполнения (CLR) языка, который представляет исполняемого файла или библиотеки динамической компоновки (DLL).</span><span class="sxs-lookup"><span data-stu-id="cdc86-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cdc86-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cdc86-104">Methods</span></span>  
  
|<span data-ttu-id="cdc86-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cdc86-105">Method</span></span>|<span data-ttu-id="cdc86-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="cdc86-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cdc86-107">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cdc86-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="cdc86-108">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="cdc86-108">Not implemented.</span></span>|  
|[<span data-ttu-id="cdc86-109">Метод EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="cdc86-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="cdc86-110">Определяет, является ли [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) , называются обратные вызовы для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="cdc86-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="cdc86-111">Метод EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="cdc86-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="cdc86-112">Определяет, сохраняет ли компилятор just-in-time (JIT), сведения об отладке для методов в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="cdc86-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="cdc86-113">Метод GetAssembly</span><span class="sxs-lookup"><span data-stu-id="cdc86-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="cdc86-114">Возвращает содержащей сборки для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="cdc86-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="cdc86-115">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="cdc86-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="cdc86-116">Получает базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="cdc86-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="cdc86-117">Метод GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="cdc86-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="cdc86-118">Возвращает ICorDebugClass из метаданных.</span><span class="sxs-lookup"><span data-stu-id="cdc86-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="cdc86-119">Метод GetEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="cdc86-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="cdc86-120">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="cdc86-120">Deprecated.</span></span>|  
|[<span data-ttu-id="cdc86-121">Метод GetFunctionFromRVA</span><span class="sxs-lookup"><span data-stu-id="cdc86-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="cdc86-122">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="cdc86-122">Not implemented.</span></span>|  
|[<span data-ttu-id="cdc86-123">Метод GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="cdc86-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="cdc86-124">Возвращает функцию, которая указывается токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="cdc86-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="cdc86-125">Метод GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="cdc86-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="cdc86-126">Возвращает объект значения для заданной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="cdc86-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="cdc86-127">Метод GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="cdc86-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="cdc86-128">Возвращает указатель на интерфейс метаданных, который может использоваться для просмотра метаданных для модуля.</span><span class="sxs-lookup"><span data-stu-id="cdc86-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="cdc86-129">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="cdc86-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="cdc86-130">Возвращает имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="cdc86-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="cdc86-131">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="cdc86-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="cdc86-132">Получает процесс, содержащий для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="cdc86-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="cdc86-133">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="cdc86-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="cdc86-134">Получает размер модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="cdc86-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="cdc86-135">Метод GetToken</span><span class="sxs-lookup"><span data-stu-id="cdc86-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="cdc86-136">Получает маркер для записи таблицы для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="cdc86-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="cdc86-137">Метод IsDynamic</span><span class="sxs-lookup"><span data-stu-id="cdc86-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="cdc86-138">Указывает, является ли динамический модуль.</span><span class="sxs-lookup"><span data-stu-id="cdc86-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="cdc86-139">Метод IsInMemory</span><span class="sxs-lookup"><span data-stu-id="cdc86-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="cdc86-140">Указывает, существует ли этот модуль только в памяти.</span><span class="sxs-lookup"><span data-stu-id="cdc86-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdc86-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="cdc86-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdc86-142">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cdc86-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdc86-143">Требования</span><span class="sxs-lookup"><span data-stu-id="cdc86-143">Requirements</span></span>  
 <span data-ttu-id="cdc86-144">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdc86-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdc86-145">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdc86-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdc86-146">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdc86-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdc86-147">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdc86-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc86-148">См. также</span><span class="sxs-lookup"><span data-stu-id="cdc86-148">See Also</span></span>  
 [<span data-ttu-id="cdc86-149">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="cdc86-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="cdc86-150">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cdc86-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
