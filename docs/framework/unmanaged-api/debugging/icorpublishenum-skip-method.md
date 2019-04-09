---
title: Метод ICorPublishEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98892964eb21746580e9115f86fd1be0832d9f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082058"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="c561c-102">Метод ICorPublishEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="c561c-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="c561c-103">Перемещение курсора вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="c561c-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c561c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c561c-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c561c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c561c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c561c-106">[in] Число элементов, по которому выполняется перемещение курсора вперед.</span><span class="sxs-lookup"><span data-stu-id="c561c-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c561c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c561c-107">Requirements</span></span>  
 <span data-ttu-id="c561c-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c561c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c561c-109">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c561c-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c561c-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c561c-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c561c-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c561c-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c561c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c561c-112">See also</span></span>

- [<span data-ttu-id="c561c-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="c561c-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
