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
ms.openlocfilehash: 230b02b71abea48b1c3ad4094ea90812493149d1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860999"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="cfb93-102">Метод ICorProfilerThreadEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="cfb93-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="cfb93-103">Возвращает число потоков, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="cfb93-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfb93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfb93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfb93-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cfb93-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cfb93-106">заполняет Число потоков, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="cfb93-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfb93-107">Требования</span><span class="sxs-lookup"><span data-stu-id="cfb93-107">Requirements</span></span>  
 <span data-ttu-id="cfb93-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfb93-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfb93-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cfb93-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cfb93-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfb93-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfb93-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfb93-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb93-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfb93-112">See also</span></span>

- [<span data-ttu-id="cfb93-113">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="cfb93-113">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="cfb93-114">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="cfb93-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
