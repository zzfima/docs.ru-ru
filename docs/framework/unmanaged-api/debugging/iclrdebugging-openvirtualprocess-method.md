---
title: Метод ICLRDebugging::OpenVirtualProcess
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
ms.openlocfilehash: 585b3d605d0df9169c12ca10198846ec0a7fe6d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793613"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="f46fc-102">Метод ICLRDebugging::OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="f46fc-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="f46fc-103">Возвращает интерфейс ICorDebugProcess, соответствующий загруженному в процесс модулю среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f46fc-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f46fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f46fc-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="f46fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f46fc-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="f46fc-106">окне Базовый адрес модуля в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="f46fc-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="f46fc-107">COR_E_NOT_CLR будет возвращен, если указанный модуль не является модулем CLR.</span><span class="sxs-lookup"><span data-stu-id="f46fc-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="f46fc-108">окне Абстракция целевого объекта данных, позволяющая управляемому отладчику проверять состояние процесса.</span><span class="sxs-lookup"><span data-stu-id="f46fc-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="f46fc-109">В отладчике должен быть реализован интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f46fc-109">The debugger must implement the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="f46fc-110">Необходимо реализовать интерфейс [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) для поддержки сценариев, в которых отлаживаемая среда CLR не установлена локально на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f46fc-110">You should implement the [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="f46fc-111">окне Интерфейс обратного вызова поставщика библиотеки, позволяющий находить и загружать библиотеки отладки для конкретных версий по запросу.</span><span class="sxs-lookup"><span data-stu-id="f46fc-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="f46fc-112">Этот параметр является обязательным только в том случае, если `ppProcess` или `pFlags` не `null`.</span><span class="sxs-lookup"><span data-stu-id="f46fc-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="f46fc-113">окне Самая высокая версия среды CLR, которую отладчик может отлаживать.</span><span class="sxs-lookup"><span data-stu-id="f46fc-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="f46fc-114">Необходимо указать основной, дополнительный номер версии и версию сборки из последней версии среды CLR, которую поддерживает этот отладчик, и установить номер редакции 65535 для размещения будущих выпусков среды CLR на месте.</span><span class="sxs-lookup"><span data-stu-id="f46fc-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="f46fc-115">окне ИДЕНТИФИКАТОР получаемого интерфейса ICorDebugProcess.</span><span class="sxs-lookup"><span data-stu-id="f46fc-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="f46fc-116">В настоящее время допустимыми значениями являются IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 и IID_CORDEBUGPROCESS.</span><span class="sxs-lookup"><span data-stu-id="f46fc-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="f46fc-117">заполняет Указатель на COM-интерфейс, идентифицируемый `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="f46fc-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f46fc-118">[вход, выход] Версия среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f46fc-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="f46fc-119">На входе это значение можно `null`.</span><span class="sxs-lookup"><span data-stu-id="f46fc-119">On input, this value can be `null`.</span></span> <span data-ttu-id="f46fc-120">Он также может указывать на структуру [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) . в этом случае поле `wStructVersion` структуры должно быть инициализировано значением 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="f46fc-120">It can also point to a [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="f46fc-121">В выходных данных Возвращаемая структура `CLR_DEBUGGING_VERSION` будет заполнена сведениями о версии для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f46fc-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="f46fc-122">заполняет Информационные флаги для указанной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f46fc-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="f46fc-123">Описание флагов см. в [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) разделе.</span><span class="sxs-lookup"><span data-stu-id="f46fc-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f46fc-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f46fc-124">Return Value</span></span>  
 <span data-ttu-id="f46fc-125">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="f46fc-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f46fc-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f46fc-126">HRESULT</span></span>|<span data-ttu-id="f46fc-127">Описание</span><span class="sxs-lookup"><span data-stu-id="f46fc-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f46fc-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="f46fc-128">S_OK</span></span>|<span data-ttu-id="f46fc-129">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="f46fc-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="f46fc-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f46fc-130">E_POINTER</span></span>|<span data-ttu-id="f46fc-131">Параметр `pDataTarget` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="f46fc-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="f46fc-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="f46fc-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="f46fc-133">Обратный вызов [иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md) возвращает ошибку или не предоставляет допустимый маркер.</span><span class="sxs-lookup"><span data-stu-id="f46fc-133">The [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="f46fc-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="f46fc-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="f46fc-135">`pDataTarget` не реализует необходимые интерфейсы целевых данных для этой версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f46fc-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="f46fc-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="f46fc-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="f46fc-137">Указанный модуль не является модулем CLR.</span><span class="sxs-lookup"><span data-stu-id="f46fc-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="f46fc-138">Это значение HRESULT также возвращается, если модуль среды CLR не удается обнаружить из-за повреждения памяти, модуль недоступен или версия среды CLR позже версии оболочки совместимости.</span><span class="sxs-lookup"><span data-stu-id="f46fc-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="f46fc-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="f46fc-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="f46fc-140">Эта версия среды выполнения не поддерживает эту модель отладки.</span><span class="sxs-lookup"><span data-stu-id="f46fc-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="f46fc-141">В настоящее время модель отладки не поддерживается версиями CLR до .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f46fc-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="f46fc-142">После этой ошибки по-прежнему будет задано правильное значение параметра `pwszVersion` Output.</span><span class="sxs-lookup"><span data-stu-id="f46fc-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="f46fc-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="f46fc-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="f46fc-144">Версия CLR больше версии, которую этот отладчик заявляет для поддержки.</span><span class="sxs-lookup"><span data-stu-id="f46fc-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="f46fc-145">После этой ошибки по-прежнему будет задано правильное значение параметра `pwszVersion` Output.</span><span class="sxs-lookup"><span data-stu-id="f46fc-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="f46fc-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="f46fc-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="f46fc-147">Интерфейс `riidProcess` недоступен.</span><span class="sxs-lookup"><span data-stu-id="f46fc-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="f46fc-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="f46fc-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="f46fc-149">Структура `CLR_DEBUGGING_VERSION` не имеет распознанного значения для `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="f46fc-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="f46fc-150">Единственным допустимым значением в данный момент является 0.</span><span class="sxs-lookup"><span data-stu-id="f46fc-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f46fc-151">Исключения</span><span class="sxs-lookup"><span data-stu-id="f46fc-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f46fc-152">Заметки</span><span class="sxs-lookup"><span data-stu-id="f46fc-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f46fc-153">Требования</span><span class="sxs-lookup"><span data-stu-id="f46fc-153">Requirements</span></span>  
 <span data-ttu-id="f46fc-154">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f46fc-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f46fc-155">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f46fc-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f46fc-156">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f46fc-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f46fc-157">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f46fc-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f46fc-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="f46fc-158">See also</span></span>

- [<span data-ttu-id="f46fc-159">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f46fc-159">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f46fc-160">Отладка</span><span class="sxs-lookup"><span data-stu-id="f46fc-160">Debugging</span></span>](index.md)
