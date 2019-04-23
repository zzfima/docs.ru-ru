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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0707351d28ef75083b7bfb6ded38bc2a8460131
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136218"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="ed349-102">Метод ICorProfilerCallback::ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="ed349-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="ed349-103">Уведомляет профилировщик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="ed349-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed349-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed349-104">Syntax</span></span>  
  
```  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed349-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed349-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ed349-106">[in] Идентифицирует класс, который вызывается при выгрузке.</span><span class="sxs-lookup"><span data-stu-id="ed349-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed349-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed349-107">Remarks</span></span>  
 <span data-ttu-id="ed349-108">Значение `classId` не является допустимым для информационного запроса после `ClassUnloadStarted` возвращает метод — это последняя возможность профилировщика для получения сведений об этом классе.</span><span class="sxs-lookup"><span data-stu-id="ed349-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed349-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ed349-109">Requirements</span></span>  
 <span data-ttu-id="ed349-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed349-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed349-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed349-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed349-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed349-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed349-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed349-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed349-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ed349-114">See also</span></span>

- [<span data-ttu-id="ed349-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ed349-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ed349-116">Метод ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="ed349-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
