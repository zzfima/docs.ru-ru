---
title: Метод ICorDebugStepper::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: a242764710d92e81e8089bc2919734bfac4bcdb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137567"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="29c01-102">Метод ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="29c01-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="29c01-103">Возвращает значение, указывающее, выполняется ли в данный момент шаг.</span><span class="sxs-lookup"><span data-stu-id="29c01-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29c01-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29c01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29c01-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="29c01-106">заполняет Возвращает `true`, если средство Организации в данный момент исполняет шаг; в противном случае возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="29c01-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29c01-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="29c01-107">Remarks</span></span>  
 <span data-ttu-id="29c01-108">Любое действие шага остается активным до тех пор, пока отладчик не получит вызов [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) , который автоматически деактивирует средство Организации.</span><span class="sxs-lookup"><span data-stu-id="29c01-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="29c01-109">Пошаговое руководство также может быть деактивировано преждевременно путем вызова [ICorDebugStepper::D еактивате](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) до достижения условия обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="29c01-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29c01-110">Требования</span><span class="sxs-lookup"><span data-stu-id="29c01-110">Requirements</span></span>  
 <span data-ttu-id="29c01-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c01-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29c01-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29c01-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29c01-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29c01-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29c01-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29c01-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
