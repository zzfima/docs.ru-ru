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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db7a033944272756a739dec39d4df11fde1d48b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178611"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="4d8e1-102">Метод ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="4d8e1-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="4d8e1-103">Уведомляет профилировщик о загрузке класса.</span><span class="sxs-lookup"><span data-stu-id="4d8e1-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d8e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d8e1-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d8e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d8e1-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="4d8e1-106">[in] Идентифицирует класс, который загружается.</span><span class="sxs-lookup"><span data-stu-id="4d8e1-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d8e1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d8e1-107">Remarks</span></span>  
 <span data-ttu-id="4d8e1-108">Значение `classId` не является допустимым для информационного запроса до [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="4d8e1-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d8e1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4d8e1-109">Requirements</span></span>  
 <span data-ttu-id="4d8e1-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d8e1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d8e1-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d8e1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d8e1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d8e1-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4d8e1-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4d8e1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d8e1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4d8e1-114">See also</span></span>

- [<span data-ttu-id="4d8e1-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4d8e1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
