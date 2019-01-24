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
ms.openlocfilehash: fdc8c274cd6949977b3e0ad5df8e1e14692ad167
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563591"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="f3b53-102">Метод ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="f3b53-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="f3b53-103">Создает копию данного объекта [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="f3b53-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b53-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3b53-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3b53-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3b53-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f3b53-106">[out] Указатель на адрес `ICorPublishEnum` объект, являющийся копией этого `ICorPublishEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="f3b53-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3b53-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f3b53-107">Requirements</span></span>  
 <span data-ttu-id="f3b53-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3b53-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3b53-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f3b53-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f3b53-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3b53-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3b53-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3b53-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b53-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f3b53-112">See also</span></span>
- [<span data-ttu-id="f3b53-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="f3b53-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
