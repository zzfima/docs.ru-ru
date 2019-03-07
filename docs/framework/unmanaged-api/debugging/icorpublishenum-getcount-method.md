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
ms.openlocfilehash: c353edf9db0a7bc7ec0a25f712527dc3c9d8cc28
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484658"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="6f4b8-102">Метод ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="6f4b8-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="6f4b8-103">Получает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="6f4b8-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f4b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f4b8-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f4b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f4b8-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="6f4b8-106">[out] Указатель на число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="6f4b8-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f4b8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="6f4b8-107">Requirements</span></span>  
 <span data-ttu-id="6f4b8-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f4b8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f4b8-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6f4b8-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6f4b8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f4b8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f4b8-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f4b8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f4b8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6f4b8-112">See also</span></span>
- [<span data-ttu-id="6f4b8-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="6f4b8-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
