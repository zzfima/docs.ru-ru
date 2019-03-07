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
ms.openlocfilehash: d19814b0c663310e977ef148ad37eb74129fd4d2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466509"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="aa8bf-102">Метод ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="aa8bf-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="aa8bf-103">Уведомляет профилировщик о загрузке класса.</span><span class="sxs-lookup"><span data-stu-id="aa8bf-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa8bf-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa8bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa8bf-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="aa8bf-106">[in] Идентифицирует класс, который загружается.</span><span class="sxs-lookup"><span data-stu-id="aa8bf-106">[in] Identifies the class that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa8bf-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa8bf-107">Remarks</span></span>  
 <span data-ttu-id="aa8bf-108">Значение `classId` не является допустимым для информационного запроса до [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="aa8bf-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa8bf-109">Требования</span><span class="sxs-lookup"><span data-stu-id="aa8bf-109">Requirements</span></span>  
 <span data-ttu-id="aa8bf-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa8bf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa8bf-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa8bf-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa8bf-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa8bf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa8bf-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8bf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aa8bf-114">See also</span></span>
- [<span data-ttu-id="aa8bf-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="aa8bf-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
