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
ms.openlocfilehash: 0ea379befab7711d1c6bc2d6005cb62d853acce9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756975"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="58e45-102">Метод ICorProfilerInfo3::EnumModules</span><span class="sxs-lookup"><span data-stu-id="58e45-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="58e45-103">Возвращает перечислитель, предоставляющий методы для последовательного перебора коллекции управляемых модулей, загруженных в приложение.</span><span class="sxs-lookup"><span data-stu-id="58e45-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58e45-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58e45-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="58e45-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="58e45-106">[out] Указатель на [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="58e45-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58e45-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="58e45-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58e45-108">Требования</span><span class="sxs-lookup"><span data-stu-id="58e45-108">Requirements</span></span>  
 <span data-ttu-id="58e45-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58e45-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e45-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58e45-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58e45-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58e45-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58e45-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e45-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e45-113">См. также</span><span class="sxs-lookup"><span data-stu-id="58e45-113">See also</span></span>

- [<span data-ttu-id="58e45-114">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="58e45-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="58e45-115">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="58e45-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="58e45-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="58e45-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="58e45-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="58e45-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
