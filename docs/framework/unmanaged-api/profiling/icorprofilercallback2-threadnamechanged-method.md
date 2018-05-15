---
title: Метод ICorProfilerCallback2::ThreadNameChanged
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6bf11d71b90f11a5d9a3844ed59a8574b7b76699
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="8e41b-102">Метод ICorProfilerCallback2::ThreadNameChanged</span><span class="sxs-lookup"><span data-stu-id="8e41b-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="8e41b-103">Уведомляет профилировщик кода об изменении имени потока.</span><span class="sxs-lookup"><span data-stu-id="8e41b-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e41b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e41b-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e41b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e41b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="8e41b-106">[in] Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="8e41b-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8e41b-107">[in] Длина имени нового потока.</span><span class="sxs-lookup"><span data-stu-id="8e41b-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="8e41b-108">[in] Новое имя потока.</span><span class="sxs-lookup"><span data-stu-id="8e41b-108">[in] The new name of the thread.</span></span> <span data-ttu-id="8e41b-109">Имя является символом null.</span><span class="sxs-lookup"><span data-stu-id="8e41b-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e41b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8e41b-110">Requirements</span></span>  
 <span data-ttu-id="8e41b-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e41b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e41b-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e41b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e41b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e41b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e41b-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e41b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e41b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8e41b-115">See Also</span></span>  
 [<span data-ttu-id="8e41b-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8e41b-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="8e41b-117">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="8e41b-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
