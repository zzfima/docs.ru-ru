---
title: Метод ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: 15ce195af0c0e8f8777f6e5d02043e17e32308da
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866654"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="69bea-102">Метод ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="69bea-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="69bea-103">Уведомляет профилировщик о том, что загрузка сборки завершена.</span><span class="sxs-lookup"><span data-stu-id="69bea-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69bea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69bea-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69bea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69bea-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="69bea-106">\[в] определяет сборку, которая была загружена.</span><span class="sxs-lookup"><span data-stu-id="69bea-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="69bea-107">\[in] значение HRESULT, указывающее, успешно ли завершена загрузка сборки.</span><span class="sxs-lookup"><span data-stu-id="69bea-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="69bea-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="69bea-108">Remarks</span></span>  
 <span data-ttu-id="69bea-109">Значение `assemblyId` недопустимо для информационного запроса, пока не будет вызван метод `AssemblyLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="69bea-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="69bea-110">Некоторые части загрузки сборки могут продолжаться после обратного вызова `AssemblyLoadFinished`.</span><span class="sxs-lookup"><span data-stu-id="69bea-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="69bea-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="69bea-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="69bea-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть загрузки сборки завершилась успешно.</span><span class="sxs-lookup"><span data-stu-id="69bea-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69bea-113">Требования</span><span class="sxs-lookup"><span data-stu-id="69bea-113">Requirements</span></span>  
 <span data-ttu-id="69bea-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69bea-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69bea-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69bea-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69bea-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69bea-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69bea-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69bea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69bea-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="69bea-118">See also</span></span>

- [<span data-ttu-id="69bea-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="69bea-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
