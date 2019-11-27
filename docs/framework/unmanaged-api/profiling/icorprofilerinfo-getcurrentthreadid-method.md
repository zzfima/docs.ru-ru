---
title: Метод ICorProfilerInfo::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: fc5356f097f869403212cd234a508f1f29c5ec94
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450389"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="83cc6-102">Метод ICorProfilerInfo::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="83cc6-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="83cc6-103">Возвращает идентификатор текущего потока, если он является управляемым потоком.</span><span class="sxs-lookup"><span data-stu-id="83cc6-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83cc6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83cc6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83cc6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83cc6-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="83cc6-106">заполняет Указатель на возвращенный идентификатор управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="83cc6-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83cc6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="83cc6-107">Remarks</span></span>  
 <span data-ttu-id="83cc6-108">Если текущий поток является внутренним потоком среды выполнения или другим неуправляемым потоком, `GetCurrentThreadID` возвращает CORPROF_E_NOT_MANAGED_THREAD как HRESULT, а возвращаемое значение параметра `pThreadId` будет равно null.</span><span class="sxs-lookup"><span data-stu-id="83cc6-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83cc6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="83cc6-109">Requirements</span></span>  
 <span data-ttu-id="83cc6-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83cc6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83cc6-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83cc6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83cc6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83cc6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83cc6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83cc6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cc6-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="83cc6-114">See also</span></span>

- [<span data-ttu-id="83cc6-115">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="83cc6-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
