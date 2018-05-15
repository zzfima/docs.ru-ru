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
ms.openlocfilehash: 3174be7237bcdbd5a12f38f04d6e67d9eb9a573e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="f3675-102">Метод ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="f3675-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="f3675-103">Возвращает маску немного, указывающее, регистрируется в это [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="f3675-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3675-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3675-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3675-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3675-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="f3675-106">[out] Битовая маска, указывающее, какие регистры, доступных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="f3675-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3675-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3675-107">Remarks</span></span>  
 <span data-ttu-id="f3675-108">Регистр может быть недоступен, если его значение нельзя определить для данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="f3675-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="f3675-109">Возвращаемая маска содержит один бит для каждого регистра (1 << индекс регистра).</span><span class="sxs-lookup"><span data-stu-id="f3675-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="f3675-110">Битовое значение равно 1, если регистр доступен, или 0, если он не доступен.</span><span class="sxs-lookup"><span data-stu-id="f3675-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3675-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f3675-111">Requirements</span></span>  
 <span data-ttu-id="f3675-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3675-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3675-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3675-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3675-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3675-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3675-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3675-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3675-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f3675-116">See Also</span></span>  
 [<span data-ttu-id="f3675-117">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="f3675-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="f3675-118">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="f3675-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
