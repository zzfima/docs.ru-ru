---
title: Метод ICorProfilerCallback::ModuleAttachedToAssembly
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: cb342b1c328daca5b3cfc0440e6f276ae54e3ed8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866186"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="8dea3-102">Метод ICorProfilerCallback::ModuleAttachedToAssembly</span><span class="sxs-lookup"><span data-stu-id="8dea3-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="8dea3-103">Уведомляет профилировщик о том, что модуль присоединен к своей родительской сборке.</span><span class="sxs-lookup"><span data-stu-id="8dea3-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dea3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8dea3-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dea3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8dea3-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8dea3-106">окне Идентификатор присоединяемого модуля.</span><span class="sxs-lookup"><span data-stu-id="8dea3-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="8dea3-107">окне ИДЕНТИФИКАТОР родительской сборки, к которой присоединен модуль.</span><span class="sxs-lookup"><span data-stu-id="8dea3-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dea3-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="8dea3-108">Remarks</span></span>  
 <span data-ttu-id="8dea3-109">Модуль можно загрузить через таблицу адресов импорта (IAT) с помощью вызова `LoadLibrary`или через ссылку на метаданные.</span><span class="sxs-lookup"><span data-stu-id="8dea3-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="8dea3-110">В результате загрузчик среды CLR имеет несколько путей кода для определения сборки, в которой находится модуль.</span><span class="sxs-lookup"><span data-stu-id="8dea3-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="8dea3-111">Таким образом, после вызова метода [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) модуль не знает, в какой сборке он находится, и получение идентификатора родительской сборки невозможно.</span><span class="sxs-lookup"><span data-stu-id="8dea3-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="8dea3-112">Метод `ModuleAttachedToAssembly` вызывается, когда модуль присоединяется к своей родительской сборке и может быть получен идентификатор его родительской сборки.</span><span class="sxs-lookup"><span data-stu-id="8dea3-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dea3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8dea3-113">Requirements</span></span>  
 <span data-ttu-id="8dea3-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dea3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dea3-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8dea3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8dea3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dea3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dea3-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dea3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dea3-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="8dea3-118">See also</span></span>

- [<span data-ttu-id="8dea3-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8dea3-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
