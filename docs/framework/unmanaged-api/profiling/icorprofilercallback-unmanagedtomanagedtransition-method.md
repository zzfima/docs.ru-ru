---
title: "Метод ICorProfilerCallback::UnmanagedToManagedTransition"
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
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1653a92563f0031fcb4c215dd58e4e1ac73030d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="52925-102">Метод ICorProfilerCallback::UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="52925-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="52925-103">Уведомляет профилировщик о переход от неуправляемого кода в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="52925-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52925-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52925-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52925-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52925-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="52925-106">[in] Идентификатор функции, которая вызывается.</span><span class="sxs-lookup"><span data-stu-id="52925-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="52925-107">[in] Значение [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) перечисления, которое указывает, произошло из-за вызова управляемого кода из неуправляемого кода или из-за возврат из неуправляемой функции, вызываемой управляемыми перехода.</span><span class="sxs-lookup"><span data-stu-id="52925-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52925-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="52925-108">Remarks</span></span>  
 <span data-ttu-id="52925-109">Если значение `reason` — COR_PRF_TRANSITION_RETURN и `functionId` не равно NULL, функция ID будет соответствовать неуправляемой функции и никогда не будет выполняться компиляция с помощью время JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="52925-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="52925-110">Неуправляемые функции имеют некоторые основные сведения, связанные с ними, такие как имя и некоторые метаданные.</span><span class="sxs-lookup"><span data-stu-id="52925-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="52925-111">Если значение `reason` является COR_PRF_TRANSITION_CALL, возможно, вызываемой функции (то есть, управляемую функцию) еще не JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="52925-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52925-112">Требования</span><span class="sxs-lookup"><span data-stu-id="52925-112">Requirements</span></span>  
 <span data-ttu-id="52925-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52925-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52925-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52925-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52925-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52925-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52925-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52925-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52925-117">См. также</span><span class="sxs-lookup"><span data-stu-id="52925-117">See Also</span></span>  
 [<span data-ttu-id="52925-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="52925-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="52925-119">Метод ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="52925-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [<span data-ttu-id="52925-120">Использование явного вызова Pinvoke в C++ (атрибут DllImport)</span><span class="sxs-lookup"><span data-stu-id="52925-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [<span data-ttu-id="52925-121">Использование взаимодействия языка C++ (неявный PInvoke)</span><span class="sxs-lookup"><span data-stu-id="52925-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
