---
title: Метод ICorProfilerModuleEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9249e6f5ee7b15d55f5518263b0ac2e31b64e993
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="87e03-102">Метод ICorProfilerModuleEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="87e03-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="87e03-103">Получает указатель интерфейса на копию этого [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="87e03-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87e03-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87e03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87e03-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="87e03-106">[out] Указатель на указатель интерфейса, который в свою очередь указывает на копию этого [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="87e03-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="87e03-107">Копия перечислителя хранит собственное состояние перечисления отдельно от этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="87e03-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="87e03-108">Однако копии Начальная позиция курсора совпадает со значением этого перечислителя текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="87e03-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87e03-109">Требования</span><span class="sxs-lookup"><span data-stu-id="87e03-109">Requirements</span></span>  
 <span data-ttu-id="87e03-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87e03-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87e03-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87e03-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87e03-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87e03-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87e03-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87e03-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e03-114">См. также</span><span class="sxs-lookup"><span data-stu-id="87e03-114">See Also</span></span>  
 [<span data-ttu-id="87e03-115">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="87e03-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="87e03-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="87e03-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
