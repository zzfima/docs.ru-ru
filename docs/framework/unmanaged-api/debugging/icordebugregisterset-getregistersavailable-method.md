---
title: "Метод ICorDebugRegisterSet::GetRegistersAvailable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fd7ff2b711d81ba1fe8fda9422587ec265dd88dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="e0c82-102">Метод ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="e0c82-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="e0c82-103">Возвращает маску немного, указывающее, регистрируется в это [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="e0c82-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0c82-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0c82-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0c82-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="e0c82-106">[out] Битовая маска, указывающее, какие регистры, доступных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="e0c82-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c82-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0c82-107">Remarks</span></span>  
 <span data-ttu-id="e0c82-108">Регистр может быть недоступен, если его значение нельзя определить для данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="e0c82-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="e0c82-109">Возвращаемая маска содержит один бит для каждого регистра (1 << индекс регистра).</span><span class="sxs-lookup"><span data-stu-id="e0c82-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="e0c82-110">Битовое значение равно 1, если регистр доступен, или 0, если он не доступен.</span><span class="sxs-lookup"><span data-stu-id="e0c82-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c82-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e0c82-111">Requirements</span></span>  
 <span data-ttu-id="e0c82-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0c82-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c82-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0c82-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0c82-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0c82-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0c82-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c82-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c82-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e0c82-116">See Also</span></span>  
 [<span data-ttu-id="e0c82-117">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="e0c82-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="e0c82-118">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="e0c82-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
