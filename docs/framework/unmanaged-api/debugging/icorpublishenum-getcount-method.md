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
ms.openlocfilehash: 0424d929f40da1faabd7456cdd85e39a59246d48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103250"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="ead84-102">Метод ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="ead84-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="ead84-103">Получает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="ead84-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ead84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ead84-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ead84-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ead84-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="ead84-106">[out] Указатель на число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="ead84-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ead84-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ead84-107">Requirements</span></span>  
 <span data-ttu-id="ead84-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ead84-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ead84-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ead84-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ead84-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ead84-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ead84-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ead84-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ead84-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ead84-112">See also</span></span>

- [<span data-ttu-id="ead84-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="ead84-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
