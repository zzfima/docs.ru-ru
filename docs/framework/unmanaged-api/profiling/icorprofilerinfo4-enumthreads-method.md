---
title: Метод ICorProfilerInfo4::EnumThreads
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: 5bea1b75e94d8011d3582d4f07d36bbc7a560502
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862221"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="52eaa-102">Метод ICorProfilerInfo4::EnumThreads</span><span class="sxs-lookup"><span data-stu-id="52eaa-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="52eaa-103">Возвращает перечислитель, предоставляющий методы для последовательного прохода по коллекции всех управляемых потоков в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="52eaa-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52eaa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52eaa-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52eaa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52eaa-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="52eaa-106">заполняет Указатель на интерфейс [икорпрофилерсреаденум](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="52eaa-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52eaa-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="52eaa-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52eaa-108">Требования</span><span class="sxs-lookup"><span data-stu-id="52eaa-108">Requirements</span></span>  
 <span data-ttu-id="52eaa-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52eaa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52eaa-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52eaa-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52eaa-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52eaa-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52eaa-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52eaa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52eaa-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="52eaa-113">See also</span></span>

- [<span data-ttu-id="52eaa-114">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="52eaa-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="52eaa-115">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="52eaa-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="52eaa-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="52eaa-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="52eaa-117">Профилирование</span><span class="sxs-lookup"><span data-stu-id="52eaa-117">Profiling</span></span>](index.md)
