---
title: Метод ICorDebugBlockingObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
ms.openlocfilehash: 3a1c4a931a61186c4737aada47ceb861e7848e7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122835"
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="c0baa-102">Метод ICorDebugBlockingObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c0baa-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="c0baa-103">Возвращает указанное число объектов [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="c0baa-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0baa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0baa-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0baa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0baa-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c0baa-106">окне Число извлекаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="c0baa-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="c0baa-107">заполняет Массив указателей на объекты [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="c0baa-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c0baa-108">заполняет Указатель на количество полученных объектов.</span><span class="sxs-lookup"><span data-stu-id="c0baa-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0baa-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0baa-109">Return Value</span></span>  
 <span data-ttu-id="c0baa-110">Этот метод возвращает следующие специфичные результаты HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c0baa-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="c0baa-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0baa-111">HRESULT</span></span>|<span data-ttu-id="c0baa-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c0baa-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0baa-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0baa-113">S_OK</span></span>|<span data-ttu-id="c0baa-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="c0baa-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c0baa-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c0baa-115">S_FALSE</span></span>|<span data-ttu-id="c0baa-116">Значение параметра `pceltFetched` не равно `celt`.</span><span class="sxs-lookup"><span data-stu-id="c0baa-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0baa-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="c0baa-117">Remarks</span></span>  
 <span data-ttu-id="c0baa-118">Этот метод работает, как типичный перечислитель COM.</span><span class="sxs-lookup"><span data-stu-id="c0baa-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="c0baa-119">Значения входного массива должны быть не меньше `celt`размера.</span><span class="sxs-lookup"><span data-stu-id="c0baa-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="c0baa-120">Массив будет заполнен либо следующими `celt` значениями в перечислении, либо со всеми оставшимися значениями, если меньше `celt` осталось.</span><span class="sxs-lookup"><span data-stu-id="c0baa-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="c0baa-121">При возврате из этого метода `pceltFetched` будут заполнены количеством полученных значений.</span><span class="sxs-lookup"><span data-stu-id="c0baa-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="c0baa-122">Если `values` содержит недопустимые указатели или точки в буфере, размер которого меньше `celt`или если `pceltFetched` является недопустимым указателем, результат не определен.</span><span class="sxs-lookup"><span data-stu-id="c0baa-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0baa-123">Хотя структуру [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) не нужно освобождать, интерфейс "ICorDebugValue" внутри него должен быть освобожден.</span><span class="sxs-lookup"><span data-stu-id="c0baa-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0baa-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c0baa-124">Requirements</span></span>  
 <span data-ttu-id="c0baa-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0baa-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0baa-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0baa-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0baa-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0baa-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0baa-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0baa-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0baa-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c0baa-129">See also</span></span>

- [<span data-ttu-id="c0baa-130">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="c0baa-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="c0baa-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c0baa-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c0baa-132">Отладка</span><span class="sxs-lookup"><span data-stu-id="c0baa-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
