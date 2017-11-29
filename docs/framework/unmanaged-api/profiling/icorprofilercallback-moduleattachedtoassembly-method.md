---
title: "Метод ICorProfilerCallback::ModuleAttachedToAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleAttachedToAssembly
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2c285a42bb48970756a54d5313d2839c76a9835c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="dafa4-102">Метод ICorProfilerCallback::ModuleAttachedToAssembly</span><span class="sxs-lookup"><span data-stu-id="dafa4-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="dafa4-103">Уведомляет профилировщик, модуль присоединяется к его родительской сборки.</span><span class="sxs-lookup"><span data-stu-id="dafa4-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dafa4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dafa4-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dafa4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dafa4-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="dafa4-106">[in] Идентификатор модуля, который прикрепляется.</span><span class="sxs-lookup"><span data-stu-id="dafa4-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="dafa4-107">[in] Идентификатор родительской сборки, к которой подключен модуль.</span><span class="sxs-lookup"><span data-stu-id="dafa4-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dafa4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="dafa4-108">Remarks</span></span>  
 <span data-ttu-id="dafa4-109">Модуль может быть загружен посредством таблицы адресов импорта (IAT), путем вызова `LoadLibrary`, или с помощью ссылки на метаданные.</span><span class="sxs-lookup"><span data-stu-id="dafa4-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="dafa4-110">В результате загрузчик общеязыковой среды выполнения (CLR) имеет несколько путей к коду для определения сборки, в которой находятся модуля.</span><span class="sxs-lookup"><span data-stu-id="dafa4-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="dafa4-111">Таким образом, возможна после того как [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) вызывается, модуль не знает, какой сборке в и получение идентификатора родительской сборки станет невозможным.</span><span class="sxs-lookup"><span data-stu-id="dafa4-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="dafa4-112">`ModuleAttachedToAssembly` Метод вызывается, когда модуль присоединяется к его родительской сборки и его родительской сборки можно получить идентификатор.</span><span class="sxs-lookup"><span data-stu-id="dafa4-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dafa4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="dafa4-113">Requirements</span></span>  
 <span data-ttu-id="dafa4-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dafa4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dafa4-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dafa4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dafa4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dafa4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dafa4-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dafa4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dafa4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="dafa4-118">See Also</span></span>  
 [<span data-ttu-id="dafa4-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="dafa4-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
