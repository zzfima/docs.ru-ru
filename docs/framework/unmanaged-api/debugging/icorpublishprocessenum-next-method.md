---
title: Метод ICorPublishProcessEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b39e0b85b80618afed80d65430ba18cb1128352d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466725"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="c1bb3-102">Метод ICorPublishProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c1bb3-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="c1bb3-103">Возвращает указанное число процессов из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="c1bb3-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1bb3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1bb3-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1bb3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1bb3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c1bb3-106">[in] Число процессов, которые требуется извлечь.</span><span class="sxs-lookup"><span data-stu-id="c1bb3-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="c1bb3-107">[out] Получить указатель на массив [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объектов, каждый из которых представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="c1bb3-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c1bb3-108">[out] Указатель на количество фактически возвращенных процессов.</span><span class="sxs-lookup"><span data-stu-id="c1bb3-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="c1bb3-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="c1bb3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1bb3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c1bb3-110">Requirements</span></span>  
 <span data-ttu-id="c1bb3-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1bb3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1bb3-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c1bb3-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c1bb3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1bb3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1bb3-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1bb3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1bb3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c1bb3-115">See also</span></span>
- [<span data-ttu-id="c1bb3-116">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="c1bb3-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
