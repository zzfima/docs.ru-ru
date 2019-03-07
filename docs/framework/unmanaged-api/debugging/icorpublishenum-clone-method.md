---
title: Метод ICorPublishEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 733f776b5ef2a4e1a004070dc06e1dc9f7ed0a7f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481512"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="8e2e6-102">Метод ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="8e2e6-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="8e2e6-103">Создает копию данного объекта [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="8e2e6-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e2e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e2e6-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e2e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e2e6-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8e2e6-106">[out] Указатель на адрес `ICorPublishEnum` объект, являющийся копией этого `ICorPublishEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="8e2e6-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e2e6-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8e2e6-107">Requirements</span></span>  
 <span data-ttu-id="8e2e6-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e2e6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e2e6-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="8e2e6-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8e2e6-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e2e6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e2e6-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e2e6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2e6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8e2e6-112">See also</span></span>
- [<span data-ttu-id="8e2e6-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="8e2e6-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
