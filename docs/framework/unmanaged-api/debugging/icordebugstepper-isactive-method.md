---
title: "Метод ICorDebugStepper::IsActive"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd919852d3e7c187dff7fc4304d0a1b42f5294e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="b301e-102">Метод ICorDebugStepper::IsActive</span><span class="sxs-lookup"><span data-stu-id="b301e-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="b301e-103">Возвращает значение, указывающее, является ли ICorDebugStepper в данный момент выполняется шаг.</span><span class="sxs-lookup"><span data-stu-id="b301e-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b301e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b301e-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b301e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b301e-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="b301e-106">[out] Возвращает `true` Если пошаговым в данный момент выполняется шаг; в противном случае возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="b301e-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b301e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b301e-107">Remarks</span></span>  
 <span data-ttu-id="b301e-108">Все действия шага остается активным, пока отладчик не получит [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) вызова, который автоматически деактивирует пошаговым.</span><span class="sxs-lookup"><span data-stu-id="b301e-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="b301e-109">Пошаговым может быть отключен путем вызова также преждевременно [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) перед обратным вызовом достигается условие.</span><span class="sxs-lookup"><span data-stu-id="b301e-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b301e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b301e-110">Requirements</span></span>  
 <span data-ttu-id="b301e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b301e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b301e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b301e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b301e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b301e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b301e-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b301e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
