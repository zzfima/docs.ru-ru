---
title: Метод ICorDebugEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e9e13c8acf4f60a7b43a9b4181bb03da8f0aa45
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497019"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="50d1b-102">Метод ICorDebugEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="50d1b-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="50d1b-103">Перемещение курсора вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="50d1b-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50d1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50d1b-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50d1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="50d1b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="50d1b-106">[in] Число элементов, по которому выполняется перемещение курсора вперед.</span><span class="sxs-lookup"><span data-stu-id="50d1b-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50d1b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="50d1b-107">Requirements</span></span>  
 <span data-ttu-id="50d1b-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50d1b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50d1b-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50d1b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50d1b-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50d1b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50d1b-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50d1b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d1b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="50d1b-112">See also</span></span>
- [<span data-ttu-id="50d1b-113">Интерфейс ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="50d1b-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
