---
title: Метод ICorProfilerCallback::ClassLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: 5b465216da39e8cf207f0614519720453c384ae9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866589"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="ecdbf-102">Метод ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="ecdbf-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="ecdbf-103">Уведомляет профилировщик о загрузке класса.</span><span class="sxs-lookup"><span data-stu-id="ecdbf-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdbf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecdbf-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecdbf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecdbf-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="ecdbf-106">\[в] определяет класс, который загружается.</span><span class="sxs-lookup"><span data-stu-id="ecdbf-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="ecdbf-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="ecdbf-107">Remarks</span></span>  
 <span data-ttu-id="ecdbf-108">Значение `classId` недопустимо для информационного запроса, пока не вызван метод [ICorProfilerCallback:: класслоадфинишед](icorprofilercallback-classloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ecdbf-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecdbf-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ecdbf-109">Requirements</span></span>  
 <span data-ttu-id="ecdbf-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecdbf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecdbf-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ecdbf-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ecdbf-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecdbf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecdbf-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecdbf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecdbf-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="ecdbf-114">See also</span></span>

- [<span data-ttu-id="ecdbf-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ecdbf-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
