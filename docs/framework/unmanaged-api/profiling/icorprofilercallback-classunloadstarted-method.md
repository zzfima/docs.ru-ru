---
title: Метод ICorProfilerCallback::ClassUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 752ebc4fcb284fbeb91a1efcda476249632adc5c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790177"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="1720f-102">Метод ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="1720f-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="1720f-103">Уведомляет профилировщик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="1720f-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1720f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1720f-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1720f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1720f-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="1720f-106">\[в] определяет класс, который выгружается.</span><span class="sxs-lookup"><span data-stu-id="1720f-106">\[in] Identifies the class that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="1720f-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="1720f-107">Remarks</span></span>  
 <span data-ttu-id="1720f-108">Значение `classId` недопустимо для информационного запроса после возврата метода `ClassUnloadStarted` — это последний шанс профилировщика получить сведения об этом классе.</span><span class="sxs-lookup"><span data-stu-id="1720f-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1720f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1720f-109">Requirements</span></span>  
 <span data-ttu-id="1720f-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1720f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1720f-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1720f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1720f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1720f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1720f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1720f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1720f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="1720f-114">See also</span></span>

- [<span data-ttu-id="1720f-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1720f-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1720f-116">Метод ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="1720f-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
