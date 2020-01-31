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
ms.openlocfilehash: e5d828b8252b47c2edddbe14713208ae8bc2d19d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777154"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="50f02-102">Метод ICorDebugManagedCallback::StepComplete</span><span class="sxs-lookup"><span data-stu-id="50f02-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="50f02-103">Уведомляет отладчик о завершении шага.</span><span class="sxs-lookup"><span data-stu-id="50f02-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50f02-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50f02-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50f02-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="50f02-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток, в котором выполнен шаг.</span><span class="sxs-lookup"><span data-stu-id="50f02-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="50f02-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором выполнен шаг.</span><span class="sxs-lookup"><span data-stu-id="50f02-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="50f02-108">окне Указатель на объект ICorDebugStepper, представляющий шаг при выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="50f02-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="50f02-109">окне Значение перечисления Кордебугстепреасон, указывающее результат отдельного шага.</span><span class="sxs-lookup"><span data-stu-id="50f02-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50f02-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="50f02-110">Remarks</span></span>  
 <span data-ttu-id="50f02-111">Средство организации пошагового режима можно использовать для продолжения пошагового выполнения, если отладка не будет завершена.</span><span class="sxs-lookup"><span data-stu-id="50f02-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50f02-112">Требования</span><span class="sxs-lookup"><span data-stu-id="50f02-112">Requirements</span></span>  
 <span data-ttu-id="50f02-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50f02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50f02-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50f02-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50f02-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50f02-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50f02-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50f02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f02-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="50f02-117">See also</span></span>

- [<span data-ttu-id="50f02-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="50f02-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
