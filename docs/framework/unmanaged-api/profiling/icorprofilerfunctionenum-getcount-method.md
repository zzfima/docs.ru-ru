---
title: Метод ICorProfilerFunctionEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5061750489c74e0385f2ce020c88518604b3167
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041546"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="e29d8-102">Метод ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="e29d8-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="e29d8-103">Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="e29d8-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e29d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e29d8-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e29d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e29d8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e29d8-106">[out] Количество функций, которые были загружены.</span><span class="sxs-lookup"><span data-stu-id="e29d8-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e29d8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e29d8-107">Requirements</span></span>  
 <span data-ttu-id="e29d8-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e29d8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e29d8-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e29d8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e29d8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e29d8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e29d8-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e29d8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e29d8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e29d8-112">See also</span></span>

- [<span data-ttu-id="e29d8-113">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="e29d8-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="e29d8-114">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="e29d8-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
