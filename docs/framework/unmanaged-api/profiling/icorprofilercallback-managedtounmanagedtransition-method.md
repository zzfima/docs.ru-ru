---
title: Метод ICorProfilerCallback::ManagedToUnmanagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b00394d0b08e7e4a02b95437908dd65a51d0a042
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084613"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="0cabd-102">Метод ICorProfilerCallback::ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="0cabd-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="0cabd-103">Уведомляет профилировщик о переходе из управляемого кода в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="0cabd-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cabd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cabd-104">Syntax</span></span>  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cabd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0cabd-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0cabd-106">[in] Идентификатор функции, которая вызывается.</span><span class="sxs-lookup"><span data-stu-id="0cabd-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="0cabd-107">[in] Значение [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) перечисление, указывающее, произошла ли переход из-за вызовов неуправляемого кода из управляемого кода или из-за возврат из управляемой функции, вызванных одной из неуправляемого.</span><span class="sxs-lookup"><span data-stu-id="0cabd-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cabd-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0cabd-108">Remarks</span></span>  
 <span data-ttu-id="0cabd-109">Если значение `reason` является COR_PRF_TRANSITION_CALL, функция, идентификатор имеет неуправляемую функцию, которая никогда не будет компилироваться с помощью компилятора just-in-time.</span><span class="sxs-lookup"><span data-stu-id="0cabd-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="0cabd-110">Неуправляемые функции имеют основные сведения, связанные с ними, такие как имя и некоторые метаданные.</span><span class="sxs-lookup"><span data-stu-id="0cabd-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="0cabd-111">Если неуправляемая функция была вызвана с помощью неявного вызова (PInvoke), среда выполнения не может определить назначение вызова и значение `functionId` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="0cabd-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="0cabd-112">Дополнительные сведения о неявный PInvoke, см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="0cabd-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cabd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0cabd-113">Requirements</span></span>  
 <span data-ttu-id="0cabd-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cabd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cabd-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0cabd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0cabd-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cabd-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0cabd-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0cabd-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0cabd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0cabd-118">See also</span></span>

- [<span data-ttu-id="0cabd-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0cabd-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0cabd-120">Метод UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="0cabd-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="0cabd-121">Использование явного вызова Pinvoke в C++ (атрибут DllImport)</span><span class="sxs-lookup"><span data-stu-id="0cabd-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
