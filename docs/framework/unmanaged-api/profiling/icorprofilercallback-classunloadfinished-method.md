---
title: Метод ICorProfilerCallback::ClassUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 5d9474f78dd8b999a37f60e0698cfd04240b897a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866576"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="afa5b-102">Метод ICorProfilerCallback::ClassUnloadFinished</span><span class="sxs-lookup"><span data-stu-id="afa5b-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="afa5b-103">Уведомляет профилировщик о завершении выгрузки класса.</span><span class="sxs-lookup"><span data-stu-id="afa5b-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afa5b-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afa5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="afa5b-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="afa5b-106">\[в] определяет класс, который был выгружен.</span><span class="sxs-lookup"><span data-stu-id="afa5b-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="afa5b-107">\[in] значение HRESULT, указывающее, успешно ли выгружен класс.</span><span class="sxs-lookup"><span data-stu-id="afa5b-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="afa5b-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="afa5b-108">Remarks</span></span>  
 <span data-ttu-id="afa5b-109">Некоторые части выгрузки класса могут продолжаться после обратного вызова `ClassUnloadFinished`.</span><span class="sxs-lookup"><span data-stu-id="afa5b-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="afa5b-110">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="afa5b-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="afa5b-111">Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть выгрузки класса успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="afa5b-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afa5b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="afa5b-112">Requirements</span></span>  
 <span data-ttu-id="afa5b-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afa5b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afa5b-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="afa5b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="afa5b-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afa5b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afa5b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afa5b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa5b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="afa5b-117">See also</span></span>

- [<span data-ttu-id="afa5b-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="afa5b-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="afa5b-119">Метод ClassUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="afa5b-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
