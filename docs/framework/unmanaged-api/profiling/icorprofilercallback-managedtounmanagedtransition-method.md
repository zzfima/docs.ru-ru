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
ms.openlocfilehash: f4f5871bdd7adf11fcc811fd40c62e3027b8e607
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426178"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="4cf0e-102">Метод ICorProfilerCallback::ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="4cf0e-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="4cf0e-103">Уведомляет профилировщик о том, что произошел переход из управляемого кода в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="4cf0e-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cf0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cf0e-104">Syntax</span></span>  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cf0e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4cf0e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4cf0e-106">окне Идентификатор вызываемой функции.</span><span class="sxs-lookup"><span data-stu-id="4cf0e-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="4cf0e-107">окне Значение перечисления [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) , указывающее, произошло ли переход из-за вызова неуправляемого кода из управляемого кода или из-за возврата из управляемой функции, вызываемой неуправляемой функцией.</span><span class="sxs-lookup"><span data-stu-id="4cf0e-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cf0e-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="4cf0e-108">Remarks</span></span>  
 <span data-ttu-id="4cf0e-109">Если значение `reason` равно COR_PRF_TRANSITION_CALL, то ИДЕНТИФИКАТОРом функции является неуправляемая функция, которая никогда не будет компилироваться с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="4cf0e-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="4cf0e-110">С неуправляемыми функциями связаны основные сведения, такие как имя и некоторые метаданные.</span><span class="sxs-lookup"><span data-stu-id="4cf0e-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="4cf0e-111">Если неуправляемая функция была вызвана с помощью неявного вызова платформы (PInvoke), среда выполнения не может определить назначение вызова, а значение `functionId` будет равно null.</span><span class="sxs-lookup"><span data-stu-id="4cf0e-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="4cf0e-112">Дополнительные сведения о неявном вызове PInvoke см. в разделе [ C++ использование Interop (неявный PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="4cf0e-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cf0e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4cf0e-113">Requirements</span></span>  
 <span data-ttu-id="4cf0e-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cf0e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cf0e-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4cf0e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4cf0e-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cf0e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cf0e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cf0e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cf0e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4cf0e-118">See also</span></span>

- [<span data-ttu-id="4cf0e-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4cf0e-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4cf0e-120">Метод UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="4cf0e-120">UnmanagedToManagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="4cf0e-121">Использование явного вызова Pinvoke в C++ (атрибут DllImport)</span><span class="sxs-lookup"><span data-stu-id="4cf0e-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
