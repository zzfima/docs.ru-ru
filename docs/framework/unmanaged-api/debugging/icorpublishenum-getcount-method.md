---
title: Метод ICorPublishEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1465a667763c12593c4bc89148d70f85371fcc67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775556"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="3022e-102">Метод ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="3022e-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="3022e-103">Получает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="3022e-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3022e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3022e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3022e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3022e-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="3022e-106">[out] Указатель на число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="3022e-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3022e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3022e-107">Requirements</span></span>  
 <span data-ttu-id="3022e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3022e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3022e-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3022e-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3022e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3022e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3022e-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3022e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3022e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3022e-112">See also</span></span>

- [<span data-ttu-id="3022e-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="3022e-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
