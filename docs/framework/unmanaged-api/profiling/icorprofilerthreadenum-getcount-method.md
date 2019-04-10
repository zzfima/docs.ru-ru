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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b02f70f22a7d35bf0fe7816a52c490f88b31217
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218437"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="b9dfb-102">Метод ICorProfilerThreadEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="b9dfb-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="b9dfb-103">Возвращает число потоков, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="b9dfb-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9dfb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9dfb-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9dfb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9dfb-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b9dfb-106">[out] Число потоков, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="b9dfb-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9dfb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b9dfb-107">Requirements</span></span>  
 <span data-ttu-id="b9dfb-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9dfb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9dfb-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9dfb-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9dfb-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9dfb-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b9dfb-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b9dfb-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b9dfb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b9dfb-112">See also</span></span>

- [<span data-ttu-id="b9dfb-113">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="b9dfb-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="b9dfb-114">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b9dfb-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
