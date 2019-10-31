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
ms.openlocfilehash: c6c361113a441df050a8e7cd5219819cc8332581
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131484"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="fa408-102">Метод ICorDebugManagedCallback2::FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="fa408-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="fa408-103">Уведомляет отладчик о том, что выполнение кода достигло точки последовательности в более ранней версии измененной функции.</span><span class="sxs-lookup"><span data-stu-id="fa408-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa408-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa408-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa408-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa408-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fa408-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий измененную функцию.</span><span class="sxs-lookup"><span data-stu-id="fa408-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fa408-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором была обнаружена точка останова сопоставления.</span><span class="sxs-lookup"><span data-stu-id="fa408-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="fa408-108">окне Указатель на объект ICorDebugFunction, представляющий версию функции, которая в данный момент выполняется в потоке.</span><span class="sxs-lookup"><span data-stu-id="fa408-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="fa408-109">окне Указатель на объект ICorDebugFunction, представляющий последнюю версию функции.</span><span class="sxs-lookup"><span data-stu-id="fa408-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="fa408-110">окне Смещение указателя инструкции в старой версии функции на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="fa408-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa408-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="fa408-111">Remarks</span></span>  
 <span data-ttu-id="fa408-112">Этот обратный вызов дает отладчику возможность перенаправить указатель инструкции в соответствующую позицию в новой версии указанной функции, вызвав метод [ICorDebugILFrame2:: RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fa408-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="fa408-113">Если отладчик не вызывает `RemapFunction` перед вызовом метода [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , среда выполнения продолжит выполнение старого кода и запустит другой обратный вызов `FunctionRemapOpportunity` в следующей точке последовательности.</span><span class="sxs-lookup"><span data-stu-id="fa408-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="fa408-114">Этот обратный вызов будет вызываться для каждого кадра, который выполняет более старую версию данной функции до тех пор, пока отладчик не возвратит значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="fa408-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa408-115">Требования</span><span class="sxs-lookup"><span data-stu-id="fa408-115">Requirements</span></span>  
 <span data-ttu-id="fa408-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa408-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa408-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa408-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa408-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa408-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa408-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa408-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa408-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fa408-120">See also</span></span>

- [<span data-ttu-id="fa408-121">Интерфейс ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="fa408-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="fa408-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fa408-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
