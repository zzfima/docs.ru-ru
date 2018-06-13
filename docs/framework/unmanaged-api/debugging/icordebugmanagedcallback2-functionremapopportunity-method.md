---
title: Метод ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc900ca20ac87ddecfd8f7adf0894af21ca5d2f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418094"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="79310-102">Метод ICorDebugManagedCallback2::FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="79310-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="79310-103">Уведомляет отладчик о том, что выполнение кода достигнет точки последовательности в более старой версии редактируемой функции.</span><span class="sxs-lookup"><span data-stu-id="79310-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79310-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79310-104">Syntax</span></span>  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79310-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79310-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="79310-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий измененную функцию.</span><span class="sxs-lookup"><span data-stu-id="79310-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="79310-107">[in] Указатель на объект ICorDebugThread, представляющий поток, на котором была обнаружена точка останова преобразования.</span><span class="sxs-lookup"><span data-stu-id="79310-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="79310-108">[in] Указатель на объект ICorDebugFunction, представляющий версию функции, которая в настоящее время выполняется в потоке.</span><span class="sxs-lookup"><span data-stu-id="79310-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="79310-109">[in] Указатель на объект ICorDebugFunction, представляющий последнюю версию функции.</span><span class="sxs-lookup"><span data-stu-id="79310-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="79310-110">[in] Смещение указателя инструкций в старой версии функции Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="79310-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79310-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="79310-111">Remarks</span></span>  
 <span data-ttu-id="79310-112">Этот обратный вызов дает отладчику возможность выполнить повторное сопоставление указателя инструкций местом в новой версии указанной функции, вызвав [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="79310-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="79310-113">Если отладчик не был вызван `RemapFunction` перед вызовом [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метода, среда выполнения будет выполняться старый код и формируют другой `FunctionRemapOpportunity` обратного вызова в следующей точке последовательности.</span><span class="sxs-lookup"><span data-stu-id="79310-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="79310-114">Этот обратный вызов будет вызываться для каждого кадра, выполняющего более старым заданной функции, пока отладчик возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="79310-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79310-115">Требования</span><span class="sxs-lookup"><span data-stu-id="79310-115">Requirements</span></span>  
 <span data-ttu-id="79310-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79310-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79310-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79310-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79310-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79310-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79310-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79310-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79310-120">См. также</span><span class="sxs-lookup"><span data-stu-id="79310-120">See Also</span></span>  
 [<span data-ttu-id="79310-121">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="79310-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="79310-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="79310-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
