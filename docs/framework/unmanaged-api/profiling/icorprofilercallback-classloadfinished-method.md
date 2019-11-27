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
ms.openlocfilehash: ef2c518f8f3f3069e93f06de89add1385cb4e45e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445115"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="5a4bc-102">Метод ICorProfilerCallback::ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="5a4bc-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="5a4bc-103">Уведомляет профилировщик о том, что загрузка класса завершена.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a4bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a4bc-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a4bc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a4bc-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5a4bc-106">окне Идентифицирует загруженный класс.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="5a4bc-107">окне Значение HRESULT, указывающее, успешно ли загружен класс.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a4bc-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="5a4bc-108">Remarks</span></span>  
 <span data-ttu-id="5a4bc-109">Значение `classId` недопустимо для информационного запроса, пока не будет вызван метод `ClassLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="5a4bc-110">Некоторые части загрузки класса могут продолжаться после обратного вызова `ClassLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="5a4bc-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="5a4bc-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть загрузки класса завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a4bc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5a4bc-113">Requirements</span></span>  
 <span data-ttu-id="5a4bc-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4bc-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a4bc-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a4bc-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a4bc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a4bc-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4bc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4bc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5a4bc-118">See also</span></span>

- [<span data-ttu-id="5a4bc-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5a4bc-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5a4bc-120">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="5a4bc-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
