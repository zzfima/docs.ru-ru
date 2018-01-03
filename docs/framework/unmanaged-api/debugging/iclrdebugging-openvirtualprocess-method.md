---
title: "Метод ICLRDebugging::OpenVirtualProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging.OpenVirtualProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1f71f42f10c3d25714998d1697b20a5ee13e055
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="14642-102">Метод ICLRDebugging::OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="14642-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="14642-103">Получает интерфейс ICorDebugProcess, соответствующий общие модуля среды CLR (CLR) загружена в процессе.</span><span class="sxs-lookup"><span data-stu-id="14642-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14642-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14642-104">Syntax</span></span>  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14642-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="14642-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="14642-106">[in] Базовый адрес модуля в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="14642-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="14642-107">COR_E_NOT_CLR возвращается, если указанный модуль не является модулем CLR.</span><span class="sxs-lookup"><span data-stu-id="14642-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="14642-108">[in] Целевой уровень абстракции данных, позволяющий управляемый отладчик для проверки состояния процесса.</span><span class="sxs-lookup"><span data-stu-id="14642-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="14642-109">Отладчик должен реализовывать [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="14642-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="14642-110">Вам следует реализовать [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) интерфейс для поддержки сценариев, где отлаживаемой среды CLR не установлена локально на компьютере.</span><span class="sxs-lookup"><span data-stu-id="14642-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="14642-111">[in] Интерфейс обратного вызова поставщика библиотеки, который позволяет зависящие от версии библиотеки отладки находить и загружать по требованию.</span><span class="sxs-lookup"><span data-stu-id="14642-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="14642-112">Этот параметр является обязательным только в том случае, если `ppProcess` или `pFlags` не `null`.</span><span class="sxs-lookup"><span data-stu-id="14642-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="14642-113">[in] Более высокая версия CLR, можно отлаживать этот отладчик.</span><span class="sxs-lookup"><span data-stu-id="14642-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="14642-114">Необходимо указать основной и дополнительный номера и версию последнюю версию среды CLR, поддерживаемой этим отладчиком построения и номер редакции равно 65 535, чтобы вместить будущих обслуживания версий среды CLR на месте.</span><span class="sxs-lookup"><span data-stu-id="14642-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="14642-115">[in] Идентификатор ICorDebugProcess-интерфейс для извлечения.</span><span class="sxs-lookup"><span data-stu-id="14642-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="14642-116">В настоящее время допустимы только значения, IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 и IID_CORDEBUGPROCESS.</span><span class="sxs-lookup"><span data-stu-id="14642-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="14642-117">[out] Указатель на COM-интерфейс, который определяется параметром `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="14642-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="14642-118">[in, out] Версия среды CLR.</span><span class="sxs-lookup"><span data-stu-id="14642-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="14642-119">На входе, это значение может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="14642-119">On input, this value can be `null`.</span></span> <span data-ttu-id="14642-120">Она также может указывать на [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) структура, в этом случае структура `wStructVersion` поле должно быть инициализировано 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="14642-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="14642-121">На выходе возвращенная `CLR_DEBUGGING_VERSION` структуры будут заполнены сведения о версии для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="14642-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="14642-122">[out] Информационные флаги заданной средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="14642-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="14642-123">В разделе [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) разделе Описание флагов.</span><span class="sxs-lookup"><span data-stu-id="14642-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14642-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="14642-124">Return Value</span></span>  
 <span data-ttu-id="14642-125">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="14642-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="14642-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14642-126">HRESULT</span></span>|<span data-ttu-id="14642-127">Описание</span><span class="sxs-lookup"><span data-stu-id="14642-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14642-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="14642-128">S_OK</span></span>|<span data-ttu-id="14642-129">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="14642-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="14642-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="14642-130">E_POINTER</span></span>|<span data-ttu-id="14642-131">Свойство `pDataTarget` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="14642-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="14642-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="14642-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="14642-133">[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) обратного вызова возвращает сообщение об ошибке или не предоставлен допустимый дескриптор.</span><span class="sxs-lookup"><span data-stu-id="14642-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="14642-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="14642-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="14642-135">`pDataTarget`не реализует необходимые интерфейсы целевых данных для этой версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="14642-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="14642-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="14642-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="14642-137">Указанный модуль не является модулем CLR.</span><span class="sxs-lookup"><span data-stu-id="14642-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="14642-138">Это значение HRESULT также возвращается, если не удается обнаружить модуль среды CLR, так как память повреждена, модуль недоступен или более поздней, чем версия оболочки версию среды CLR.</span><span class="sxs-lookup"><span data-stu-id="14642-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="14642-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="14642-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="14642-140">Эта версия среды выполнения не поддерживает данную модель отладки.</span><span class="sxs-lookup"><span data-stu-id="14642-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="14642-141">В настоящее время эта модель отладки не поддерживается версиями CLR перед [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14642-141">Currently, the debugging model is not supported by CLR versions before the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="14642-142">`pwszVersion` Выходной параметр по-прежнему задано правильное значение после данной ошибки.</span><span class="sxs-lookup"><span data-stu-id="14642-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="14642-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="14642-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="14642-144">Версии среды CLR больше, чем версия этот отладчик для поддержки утверждения.</span><span class="sxs-lookup"><span data-stu-id="14642-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="14642-145">`pwszVersion` Выходной параметр по-прежнему задано правильное значение после данной ошибки.</span><span class="sxs-lookup"><span data-stu-id="14642-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="14642-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="14642-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="14642-147">`riidProcess` Интерфейс недоступен.</span><span class="sxs-lookup"><span data-stu-id="14642-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="14642-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="14642-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="14642-149">`CLR_DEBUGGING_VERSION` Структура не имеет является распознанным значением `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="14642-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="14642-150">В настоящее время единственным допустимым значением является 0.</span><span class="sxs-lookup"><span data-stu-id="14642-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="14642-151">Исключения</span><span class="sxs-lookup"><span data-stu-id="14642-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14642-152">Примечания</span><span class="sxs-lookup"><span data-stu-id="14642-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14642-153">Требования</span><span class="sxs-lookup"><span data-stu-id="14642-153">Requirements</span></span>  
 <span data-ttu-id="14642-154">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14642-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14642-155">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14642-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14642-156">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14642-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14642-157">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14642-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14642-158">См. также</span><span class="sxs-lookup"><span data-stu-id="14642-158">See Also</span></span>  
 [<span data-ttu-id="14642-159">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="14642-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="14642-160">Отладка</span><span class="sxs-lookup"><span data-stu-id="14642-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
