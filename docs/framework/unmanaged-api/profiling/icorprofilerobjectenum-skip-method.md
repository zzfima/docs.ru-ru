---
title: Метод ICorProfilerObjectEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7d1273c51dcfb63e3671b7b9d893e1022d55247
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473088"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="a95e2-102">Метод ICorProfilerObjectEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="a95e2-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="a95e2-103">Перемещает курсор этого перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="a95e2-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a95e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a95e2-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a95e2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a95e2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a95e2-106">[in] Число элементов, которые нужно пропустить.</span><span class="sxs-lookup"><span data-stu-id="a95e2-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a95e2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a95e2-107">Remarks</span></span>  
 <span data-ttu-id="a95e2-108">Новое положение курсора данного перечислителя: (текущая позиция) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="a95e2-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a95e2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a95e2-109">Requirements</span></span>  
 <span data-ttu-id="a95e2-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a95e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a95e2-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a95e2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a95e2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a95e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a95e2-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a95e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a95e2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a95e2-114">See also</span></span>
- [<span data-ttu-id="a95e2-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="a95e2-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
