---
title: Метод ICorProfilerThreadEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: b08a501f7d55fbb193afd8c297ca7725348dac76
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860934"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="2cabd-102">Метод ICorProfilerThreadEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="2cabd-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="2cabd-103">Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="2cabd-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cabd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cabd-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cabd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2cabd-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2cabd-106">окне Число пропущенных элементов.</span><span class="sxs-lookup"><span data-stu-id="2cabd-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2cabd-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2cabd-107">Return Value</span></span>  
 <span data-ttu-id="2cabd-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="2cabd-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2cabd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2cabd-109">HRESULT</span></span>|<span data-ttu-id="2cabd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2cabd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2cabd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cabd-111">S_OK</span></span>|<span data-ttu-id="2cabd-112">элементы `celt` пропущены.</span><span class="sxs-lookup"><span data-stu-id="2cabd-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="2cabd-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2cabd-113">S_FALSE</span></span>|<span data-ttu-id="2cabd-114">Пропущено менее `celt` элементов, что означает, что больше нет элементов.</span><span class="sxs-lookup"><span data-stu-id="2cabd-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cabd-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="2cabd-115">Remarks</span></span>  
 <span data-ttu-id="2cabd-116">Новая позиции курсора перечислителя — (Текущая позиции) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="2cabd-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cabd-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2cabd-117">Requirements</span></span>  
 <span data-ttu-id="2cabd-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cabd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cabd-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cabd-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2cabd-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cabd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cabd-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cabd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cabd-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="2cabd-122">See also</span></span>

- [<span data-ttu-id="2cabd-123">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="2cabd-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="2cabd-124">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="2cabd-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
