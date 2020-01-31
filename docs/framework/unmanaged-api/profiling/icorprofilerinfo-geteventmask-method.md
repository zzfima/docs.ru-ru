---
title: Метод ICorProfilerInfo::GetEventMask
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
ms.openlocfilehash: 63f19fe899abd75380249e171f248480949bc471
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863911"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="bdb39-102">Метод ICorProfilerInfo::GetEventMask</span><span class="sxs-lookup"><span data-stu-id="bdb39-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="bdb39-103">Получает текущие категории событий, о которых профилировщик хочет получать уведомления из среды CLR.</span><span class="sxs-lookup"><span data-stu-id="bdb39-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdb39-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdb39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdb39-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="bdb39-106">[из] Указатель на 4-байтовое значение, определяющее категории событий.</span><span class="sxs-lookup"><span data-stu-id="bdb39-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="bdb39-107">Каждый бит управляет отдельной возможностью, поведением или типом события.</span><span class="sxs-lookup"><span data-stu-id="bdb39-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="bdb39-108">Биты описаны в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="bdb39-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdb39-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="bdb39-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bdb39-110">Вместо этого метода следует вызвать метод [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bdb39-110">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="bdb39-111">Несмотря на то, что метод `SetEventMask` поддерживается, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) предоставляет дополнительные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="bdb39-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb39-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bdb39-112">Requirements</span></span>  
 <span data-ttu-id="bdb39-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdb39-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdb39-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bdb39-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bdb39-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdb39-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdb39-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdb39-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb39-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="bdb39-117">See also</span></span>

- [<span data-ttu-id="bdb39-118">Метод GetEventMask2</span><span class="sxs-lookup"><span data-stu-id="bdb39-118">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="bdb39-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="bdb39-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
