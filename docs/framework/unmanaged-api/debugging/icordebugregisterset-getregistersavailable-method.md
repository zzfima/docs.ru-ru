---
title: Метод ICorDebugRegisterSet::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d600b4687b86f5872f94a60ad3422be764cf5307
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747204"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="8d744-102">Метод ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="8d744-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="8d744-103">Получает маску немного, указывающее, который регистрирует в этом [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="8d744-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d744-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d744-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d744-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d744-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="8d744-106">[out] Битовая маска, которая указывает, какие регистры в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="8d744-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d744-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d744-107">Remarks</span></span>  
 <span data-ttu-id="8d744-108">Регистр может быть недоступен, если его значение нельзя определить для данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="8d744-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="8d744-109">Возвращаемая маска содержит один бит для каждого из регистров (1 << индекс регистра).</span><span class="sxs-lookup"><span data-stu-id="8d744-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="8d744-110">Битовое значение равно 1, если регистр доступен, или 0, если он не доступен.</span><span class="sxs-lookup"><span data-stu-id="8d744-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d744-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8d744-111">Requirements</span></span>  
 <span data-ttu-id="8d744-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d744-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d744-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d744-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d744-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d744-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d744-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d744-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d744-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8d744-116">See also</span></span>

- [<span data-ttu-id="8d744-117">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="8d744-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="8d744-118">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="8d744-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
