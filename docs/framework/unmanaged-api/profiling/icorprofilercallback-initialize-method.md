---
title: Метод ICorProfilerCallback::Initialize
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: e4a003b30c495852a3a68d44d92bef35c3ed7812
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866303"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="6b8cb-102">Метод ICorProfilerCallback::Initialize</span><span class="sxs-lookup"><span data-stu-id="6b8cb-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="6b8cb-103">Вызывается для инициализации профилировщика кода при запуске нового приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6b8cb-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b8cb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b8cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b8cb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b8cb-105">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="6b8cb-106">\[в] указатель на интерфейс [IUnknown](/cpp/atl/iunknown) , который профилировщик должен запрашивать для указателя интерфейса [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6b8cb-106">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="6b8cb-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="6b8cb-107">Remarks</span></span>  
 <span data-ttu-id="6b8cb-108">Вызов `Initialize` является единственной возможностью включать (или отключать) обратные вызовы, которые являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="6b8cb-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="6b8cb-109">После включения обратного вызова в `Initialize` вызове его нельзя отключить позже с помощью команды [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="6b8cb-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="6b8cb-110">Значение COR_PRF_MONITOR_IMMUTABLE перечисления [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) указывает, какие события являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="6b8cb-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b8cb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6b8cb-111">Requirements</span></span>  
 <span data-ttu-id="6b8cb-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b8cb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b8cb-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6b8cb-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6b8cb-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b8cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b8cb-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b8cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8cb-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b8cb-116">See also</span></span>

- [<span data-ttu-id="6b8cb-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6b8cb-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6b8cb-118">Метод Shutdown</span><span class="sxs-lookup"><span data-stu-id="6b8cb-118">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
