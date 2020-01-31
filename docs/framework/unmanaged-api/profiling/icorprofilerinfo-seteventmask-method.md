---
title: Метод ICorProfilerInfo::SetEventMask
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
ms.openlocfilehash: ed39411fa88c38da58e8a881c47d19b3b8c9ff8d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869282"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="3a598-102">Метод ICorProfilerInfo::SetEventMask</span><span class="sxs-lookup"><span data-stu-id="3a598-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="3a598-103">Определяет значение, указывающее типы событий, для которых профилировщик хочет получать уведомления от среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3a598-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a598-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a598-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a598-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a598-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="3a598-106">[в] 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="3a598-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="3a598-107">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="3a598-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="3a598-108">Биты описаны в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3a598-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a598-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="3a598-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a598-110">Вместо этого метода следует вызвать метод [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3a598-110">You should call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="3a598-111">Несмотря на то, что метод `SetEventMask` поддерживается, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) предоставляет дополнительные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="3a598-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a598-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3a598-112">Requirements</span></span>  
 <span data-ttu-id="3a598-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a598-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a598-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a598-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a598-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a598-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a598-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a598-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a598-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a598-117">See also</span></span>

- [<span data-ttu-id="3a598-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="3a598-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3a598-119">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="3a598-119">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
