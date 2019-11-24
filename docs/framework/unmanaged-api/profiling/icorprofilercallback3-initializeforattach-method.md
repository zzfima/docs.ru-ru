---
title: Метод ICorProfilerCallback3::InitializeForAttach
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.InitializeForAttach Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::InitializeForAttach
helpviewer_keywords:
- InitializeForAttach method [.NET Framework profiling]
- ICorProfilerCallback3::InitializeForAttach method [.NET Framework profiling]
ms.assetid: bed097b3-6d52-46c9-bee7-ac7910b6fc3f
topic_type:
- apiref
ms.openlocfilehash: 047516574595f9ffcd61360f51823da73a2f9733
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439518"
---
# <a name="icorprofilercallback3initializeforattach-method"></a><span data-ttu-id="dfb09-102">Метод ICorProfilerCallback3::InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="dfb09-102">ICorProfilerCallback3::InitializeForAttach Method</span></span>
<span data-ttu-id="dfb09-103">Вызывается средой CLR, чтобы предоставить профилировщику возможность инициализировать свое состояние после операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="dfb09-103">Called by the common language runtime (CLR) to give the profiler an opportunity to initialize its state after an attach operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfb09-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForAttach(  
            [in] IUnknown * pCorProfilerInfoUnk,  
            [in] void * pvClientData,  
            [in] UINT cbClientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfb09-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfb09-105">Parameters</span></span>  
 `pCorProfilerInfoUnk`  
 <span data-ttu-id="dfb09-106">[in] Указатель интерфейса для интерфейса `ICorProfilerInfo*`.</span><span class="sxs-lookup"><span data-stu-id="dfb09-106">[in] An interface pointer for the `ICorProfilerInfo*` interface.</span></span>  
  
 `pvClientData`  
 <span data-ttu-id="dfb09-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span><span class="sxs-lookup"><span data-stu-id="dfb09-107">[in] A pointer to the data passed to the [IClrProfiling::AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method in its `pvClientData` parameter.</span></span> <span data-ttu-id="dfb09-108">Если этот параметр имеет значение null, `cbClientData` будет иметь значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="dfb09-108">If this parameter is null, `cbClientData` will be 0 (zero).</span></span> <span data-ttu-id="dfb09-109">Среда CLR освобождает эту память при возврате из `InitializeForAttach`.</span><span class="sxs-lookup"><span data-stu-id="dfb09-109">The CLR frees this memory when it returns from `InitializeForAttach`.</span></span>  
  
 `cbClientData`  
 <span data-ttu-id="dfb09-110">[in] Размер в байтах данных, на которые указывает `pvClientData`.</span><span class="sxs-lookup"><span data-stu-id="dfb09-110">[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfb09-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="dfb09-111">Remarks</span></span>  
 <span data-ttu-id="dfb09-112">Среда CLR вызывает `InitializeForAttach`, чтобы предоставить профилировщику возможность запрашивать обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="dfb09-112">The CLR calls `InitializeForAttach` to give the profiler an opportunity to request callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb09-113">Требования</span><span class="sxs-lookup"><span data-stu-id="dfb09-113">Requirements</span></span>  
 <span data-ttu-id="dfb09-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb09-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb09-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dfb09-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dfb09-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfb09-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfb09-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb09-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb09-118">См. также</span><span class="sxs-lookup"><span data-stu-id="dfb09-118">See also</span></span>

- [<span data-ttu-id="dfb09-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="dfb09-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="dfb09-120">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="dfb09-120">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="dfb09-121">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="dfb09-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="dfb09-122">Профилирование</span><span class="sxs-lookup"><span data-stu-id="dfb09-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
