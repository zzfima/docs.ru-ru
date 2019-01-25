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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f76a3cb232042ba6b91046d1f7b6e1d46ad6faef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634861"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="c7ddc-102">Метод ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="c7ddc-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="c7ddc-103">Уведомляет профилировщик об окончании загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="c7ddc-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ddc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7ddc-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7ddc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7ddc-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="c7ddc-106">[in] Идентифицирует сборку, которая была загружена.</span><span class="sxs-lookup"><span data-stu-id="c7ddc-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c7ddc-107">[in] Значение HRESULT, указывающее, является ли сборка Загрузка завершена успешно.</span><span class="sxs-lookup"><span data-stu-id="c7ddc-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7ddc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7ddc-108">Remarks</span></span>  
 <span data-ttu-id="c7ddc-109">Значение `assemblyId` не является допустимым для информационного запроса до `AssemblyLoadFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="c7ddc-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="c7ddc-110">Некоторые части загрузки сборки может по-прежнему после `AssemblyLoadFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="c7ddc-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="c7ddc-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="c7ddc-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c7ddc-112">Тем не менее значение HRESULT в `hrStatus` указывает только что первая часть загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="c7ddc-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ddc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c7ddc-113">Requirements</span></span>  
 <span data-ttu-id="c7ddc-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ddc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ddc-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7ddc-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7ddc-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ddc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ddc-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ddc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ddc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c7ddc-118">See also</span></span>
- [<span data-ttu-id="c7ddc-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c7ddc-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
