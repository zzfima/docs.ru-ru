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
ms.openlocfilehash: e0ce1d8c0074f62d35e16465b368269e233a713b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105135"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="3521e-102">Метод ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="3521e-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="3521e-103">Создает копию данного объекта [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="3521e-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3521e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3521e-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3521e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3521e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3521e-106">[out] Указатель на адрес `ICorPublishEnum` объект, являющийся копией этого `ICorPublishEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="3521e-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3521e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3521e-107">Requirements</span></span>  
 <span data-ttu-id="3521e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3521e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3521e-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3521e-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3521e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3521e-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3521e-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3521e-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3521e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3521e-112">See also</span></span>

- [<span data-ttu-id="3521e-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="3521e-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
