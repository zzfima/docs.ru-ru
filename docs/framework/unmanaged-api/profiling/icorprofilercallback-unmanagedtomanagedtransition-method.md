---
title: Метод ICorProfilerCallback::UnmanagedToManagedTransition
ms.date: 03/30/2017
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
ms.openlocfilehash: c381d4a85a1e836f1972060c8182dd698bb27550
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870556"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="238a6-102">Метод ICorProfilerCallback::UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="238a6-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="238a6-103">Уведомляет профилировщик о том, что произошел переход из неуправляемого кода в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="238a6-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="238a6-104">Syntax</span></span>  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="238a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="238a6-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="238a6-106">окне Идентификатор вызываемой функции.</span><span class="sxs-lookup"><span data-stu-id="238a6-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="238a6-107">окне Значение перечисления [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) , указывающее, произошло ли переход из-за вызова управляемого кода из неуправляемого кода или из-за возврата из неуправляемой функции, вызванной управляемой.</span><span class="sxs-lookup"><span data-stu-id="238a6-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="238a6-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="238a6-108">Remarks</span></span>  
 <span data-ttu-id="238a6-109">Если значение `reason` равно COR_PRF_TRANSITION_RETURN и `functionId` не равно null, то ИДЕНТИФИКАТОРом функции является неуправляемая функция и никогда не будет компилироваться с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="238a6-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="238a6-110">С неуправляемыми функциями связаны некоторые основные сведения, такие как имя и некоторые метаданные.</span><span class="sxs-lookup"><span data-stu-id="238a6-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="238a6-111">Если значение `reason` имеет COR_PRF_TRANSITION_CALL, возможно, что вызванная функция (то есть управляемая функция) еще не скомпилирована с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="238a6-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238a6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="238a6-112">Requirements</span></span>  
 <span data-ttu-id="238a6-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="238a6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238a6-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="238a6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="238a6-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="238a6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="238a6-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="238a6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238a6-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="238a6-117">See also</span></span>

- [<span data-ttu-id="238a6-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="238a6-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="238a6-119">Метод ManagedToUnmanagedTransition</span><span class="sxs-lookup"><span data-stu-id="238a6-119">ManagedToUnmanagedTransition Method</span></span>](icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="238a6-120">Использование явного вызова Pinvoke в C++ (атрибут DllImport)</span><span class="sxs-lookup"><span data-stu-id="238a6-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="238a6-121">Использование взаимодействия языка C++ (неявный PInvoke)</span><span class="sxs-lookup"><span data-stu-id="238a6-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
