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
ms.openlocfilehash: 53b892cddbf716afbd137ead36a69aa42f22d331
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752228"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="1af03-102">Метод ICorDebugEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="1af03-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="1af03-103">Перемещение курсора вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="1af03-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1af03-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1af03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1af03-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1af03-106">[in] Число элементов, по которому выполняется перемещение курсора вперед.</span><span class="sxs-lookup"><span data-stu-id="1af03-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af03-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1af03-107">Requirements</span></span>  
 <span data-ttu-id="1af03-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1af03-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af03-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1af03-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1af03-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1af03-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1af03-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af03-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af03-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1af03-112">See also</span></span>

- [<span data-ttu-id="1af03-113">Интерфейс ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="1af03-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
