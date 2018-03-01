---
title: "Метод ICorProfilerFunctionEnum::Clone"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 449292d8bacd6bb965119da81671c739f12dc3a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="929d9-102">Метод ICorProfilerFunctionEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="929d9-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="929d9-103">Получает указатель интерфейса на копию этого [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="929d9-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="929d9-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="929d9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="929d9-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="929d9-106">[out] Указатель на указатель интерфейса, который в свою очередь, указывает на копию этого [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="929d9-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="929d9-107">Копия перечислителя хранит собственное состояние перечисления отдельно от этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="929d9-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="929d9-108">Однако копии Начальная позиция курсора совпадает со значением этого перечислителя текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="929d9-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929d9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="929d9-109">Requirements</span></span>  
 <span data-ttu-id="929d9-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="929d9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929d9-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="929d9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="929d9-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="929d9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="929d9-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="929d9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929d9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="929d9-114">See Also</span></span>  
 [<span data-ttu-id="929d9-115">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="929d9-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="929d9-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="929d9-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
