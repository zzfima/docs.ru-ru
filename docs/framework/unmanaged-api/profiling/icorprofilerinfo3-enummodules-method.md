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
ms.openlocfilehash: be5d05c34272b9fa5755b4d0e22fa9094707c5ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093882"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="9dbb3-102">Метод ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="9dbb3-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="9dbb3-103">Возвращает перечислитель, предоставляющий методы для последовательного перебора коллекции управляемых модулей, загруженных в приложение.</span><span class="sxs-lookup"><span data-stu-id="9dbb3-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbb3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dbb3-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dbb3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dbb3-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9dbb3-106">[out] Указатель на [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9dbb3-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dbb3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9dbb3-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dbb3-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9dbb3-108">Requirements</span></span>  
 <span data-ttu-id="9dbb3-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dbb3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dbb3-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9dbb3-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9dbb3-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dbb3-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9dbb3-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9dbb3-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9dbb3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9dbb3-113">See also</span></span>

- [<span data-ttu-id="9dbb3-114">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="9dbb3-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="9dbb3-115">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="9dbb3-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="9dbb3-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="9dbb3-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="9dbb3-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="9dbb3-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
