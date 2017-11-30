---
title: "Метод ICorPublishProcessEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcessEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6823a8d973b997576da3271c85234b347f1c8562
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="c4166-102">Метод ICorPublishProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c4166-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="c4166-103">Возвращает заданное число процессов из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="c4166-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4166-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4166-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4166-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4166-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c4166-106">[in] Число процессов должно быть извлечено.</span><span class="sxs-lookup"><span data-stu-id="c4166-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="c4166-107">[out] Получить указатель на массив [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объектов, каждый из которых представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="c4166-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c4166-108">[out] Указатель на число фактически извлеченных процессов.</span><span class="sxs-lookup"><span data-stu-id="c4166-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="c4166-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="c4166-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4166-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c4166-110">Requirements</span></span>  
 <span data-ttu-id="c4166-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4166-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4166-112">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c4166-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c4166-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4166-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4166-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4166-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4166-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c4166-115">See Also</span></span>  
 [<span data-ttu-id="c4166-116">ICorPublishProcessEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c4166-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
