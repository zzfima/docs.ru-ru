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
ms.openlocfilehash: 9053505f7356f4618993ead911f730909f53f383
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227149"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="9fca4-102">Метод ICorProfilerModuleEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="9fca4-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="9fca4-103">Получает указатель интерфейса на копию этого [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9fca4-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fca4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fca4-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fca4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9fca4-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9fca4-106">[out] Указатель на указатель интерфейса, в свою очередь указывает на копию данного объекта [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9fca4-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="9fca4-107">Копия перечислителя хранит собственное состояние перечисления отдельно от этот перечислитель.</span><span class="sxs-lookup"><span data-stu-id="9fca4-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="9fca4-108">Тем не менее позиция курсора начальной копии совпадает с текущей позицией курсора этот перечислитель.</span><span class="sxs-lookup"><span data-stu-id="9fca4-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fca4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9fca4-109">Requirements</span></span>  
 <span data-ttu-id="9fca4-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fca4-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fca4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fca4-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fca4-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9fca4-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9fca4-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fca4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9fca4-114">See also</span></span>

- [<span data-ttu-id="9fca4-115">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="9fca4-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="9fca4-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="9fca4-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
