---
title: Метод ICorDebugManagedCallback::StepComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cd6cce73a96cf522521d7cd8d0cc8024e95b93c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413261"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="4f04f-102">Метод ICorDebugManagedCallback::StepComplete</span><span class="sxs-lookup"><span data-stu-id="4f04f-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="4f04f-103">Уведомляет отладчик о выполнении шага.</span><span class="sxs-lookup"><span data-stu-id="4f04f-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f04f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f04f-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f04f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f04f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4f04f-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий поток, в котором шага.</span><span class="sxs-lookup"><span data-stu-id="4f04f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4f04f-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором шага.</span><span class="sxs-lookup"><span data-stu-id="4f04f-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="4f04f-108">[in] Указатель на объект ICorDebugStepper, представляющее шаг при выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="4f04f-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="4f04f-109">[in] Значение перечисления CorDebugStepReason, которое указывает результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="4f04f-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f04f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f04f-110">Remarks</span></span>  
 <span data-ttu-id="4f04f-111">Пошаговым можно продолжить пошаговое выполнение при необходимости, если отладка завершена.</span><span class="sxs-lookup"><span data-stu-id="4f04f-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f04f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4f04f-112">Requirements</span></span>  
 <span data-ttu-id="4f04f-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f04f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f04f-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f04f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f04f-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f04f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f04f-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f04f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f04f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4f04f-117">See Also</span></span>  
 [<span data-ttu-id="4f04f-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="4f04f-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
