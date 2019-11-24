---
title: Метод ICorProfilerThreadEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
ms.openlocfilehash: 695b720119854de4645b2f14dd55811f2465504a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447641"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="37b54-102">Метод ICorProfilerThreadEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="37b54-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="37b54-103">Возвращает число потоков, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="37b54-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37b54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37b54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37b54-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="37b54-106">[out] The number of threads used by the application.</span><span class="sxs-lookup"><span data-stu-id="37b54-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b54-107">Требования</span><span class="sxs-lookup"><span data-stu-id="37b54-107">Requirements</span></span>  
 <span data-ttu-id="37b54-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37b54-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b54-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37b54-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37b54-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37b54-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37b54-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b54-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b54-112">См. также</span><span class="sxs-lookup"><span data-stu-id="37b54-112">See also</span></span>

- [<span data-ttu-id="37b54-113">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="37b54-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="37b54-114">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="37b54-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
