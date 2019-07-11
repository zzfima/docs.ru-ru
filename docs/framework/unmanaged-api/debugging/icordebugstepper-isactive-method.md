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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dde27f74ac59d033b6e25fba1dbb8e52c4b91af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760677"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="7aa7b-102">Метод ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="7aa7b-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="7aa7b-103">Получает значение, указывающее, ли ICorDebugStepper момент выполняет этап.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7aa7b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7aa7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7aa7b-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="7aa7b-106">[out] Возвращает `true` Если несопоставимого в данный момент выполняет этап; в противном случае возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7aa7b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7aa7b-107">Remarks</span></span>  
 <span data-ttu-id="7aa7b-108">Любое действие шага остается активным, пока отладчик не получит [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) вызов, который автоматически деактивирует несопоставимого.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="7aa7b-109">Шаг может быть отключен путем вызова также преждевременно [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) перед обратным вызовом достижении условия.</span><span class="sxs-lookup"><span data-stu-id="7aa7b-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa7b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7aa7b-110">Requirements</span></span>  
 <span data-ttu-id="7aa7b-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aa7b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aa7b-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7aa7b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7aa7b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7aa7b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7aa7b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aa7b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
