---
title: Метод ICorProfilerInfo3::EnumModules
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8045e689353a047870c1d93022132846f37dc165
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="b8c3d-102">Метод ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="b8c3d-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="b8c3d-103">Возвращает перечислитель, предоставляющий методы для последовательного перебора коллекции управляемых модулей, загруженных в приложение.</span><span class="sxs-lookup"><span data-stu-id="b8c3d-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8c3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8c3d-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8c3d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8c3d-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b8c3d-106">[out] Указатель на [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b8c3d-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8c3d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b8c3d-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8c3d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b8c3d-108">Requirements</span></span>  
 <span data-ttu-id="b8c3d-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8c3d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8c3d-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8c3d-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8c3d-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8c3d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8c3d-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8c3d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8c3d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b8c3d-113">See Also</span></span>  
 [<span data-ttu-id="b8c3d-114">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="b8c3d-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="b8c3d-115">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="b8c3d-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="b8c3d-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b8c3d-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="b8c3d-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="b8c3d-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
