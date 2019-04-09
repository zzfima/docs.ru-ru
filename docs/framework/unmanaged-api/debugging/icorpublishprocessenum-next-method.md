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
ms.openlocfilehash: 169716d1a6d0dd633821cc832de96c9a02958d76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183109"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="fb70b-102">Метод ICorPublishProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="fb70b-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="fb70b-103">Возвращает указанное число процессов из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="fb70b-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb70b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb70b-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb70b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb70b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fb70b-106">[in] Число процессов, которые требуется извлечь.</span><span class="sxs-lookup"><span data-stu-id="fb70b-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="fb70b-107">[out] Получить указатель на массив [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объектов, каждый из которых представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="fb70b-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fb70b-108">[out] Указатель на количество фактически возвращенных процессов.</span><span class="sxs-lookup"><span data-stu-id="fb70b-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="fb70b-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="fb70b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb70b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fb70b-110">Requirements</span></span>  
 <span data-ttu-id="fb70b-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb70b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb70b-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="fb70b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fb70b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb70b-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fb70b-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fb70b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb70b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fb70b-115">See also</span></span>

- [<span data-ttu-id="fb70b-116">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="fb70b-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
