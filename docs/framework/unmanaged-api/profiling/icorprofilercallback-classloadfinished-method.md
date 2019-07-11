---
title: Метод ICorProfilerCallback::ClassLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6508c989b143780090d582fd4175fe20bedeb770
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745436"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="55e3f-102">Метод ICorProfilerCallback::ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="55e3f-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="55e3f-103">Уведомляет профилировщик об окончании загрузки класса.</span><span class="sxs-lookup"><span data-stu-id="55e3f-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55e3f-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e3f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55e3f-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="55e3f-106">[in] Идентифицирует класс, который был загружен.</span><span class="sxs-lookup"><span data-stu-id="55e3f-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="55e3f-107">[in] Значение HRESULT, указывающее, успешно ли загружен класс.</span><span class="sxs-lookup"><span data-stu-id="55e3f-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55e3f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="55e3f-108">Remarks</span></span>  
 <span data-ttu-id="55e3f-109">Значение `classId` не является допустимым для информационного запроса до `ClassLoadFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="55e3f-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="55e3f-110">Загрузка класса некоторых частей может по-прежнему после `ClassLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="55e3f-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="55e3f-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="55e3f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="55e3f-112">Тем не менее значение HRESULT в `hrStatus` указывает, что первая часть загрузки класса выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="55e3f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e3f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="55e3f-113">Requirements</span></span>  
 <span data-ttu-id="55e3f-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55e3f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e3f-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55e3f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55e3f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55e3f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55e3f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e3f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e3f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="55e3f-118">See also</span></span>

- [<span data-ttu-id="55e3f-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="55e3f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="55e3f-120">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="55e3f-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
