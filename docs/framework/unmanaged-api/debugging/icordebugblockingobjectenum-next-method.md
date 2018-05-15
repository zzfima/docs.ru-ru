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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4336978825fbf7844b3ceaf179954f28660f08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugblockingobjectenumnext-method"></a><span data-ttu-id="465c7-102">Метод ICorDebugBlockingObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="465c7-102">ICorDebugBlockingObjectEnum::Next Method</span></span>
<span data-ttu-id="465c7-103">Возвращает заданное число [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) объекты из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="465c7-103">Gets the specified number of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="465c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="465c7-104">Syntax</span></span>  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="465c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="465c7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="465c7-106">[in] Количество объектов для извлечения.</span><span class="sxs-lookup"><span data-stu-id="465c7-106">[in] The number of objects to retrieve.</span></span>  
  
 `values`  
 <span data-ttu-id="465c7-107">[out] Массив указателей на [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="465c7-107">[out] An array of pointers to [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) objects.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="465c7-108">[out] Указатель на число объектов, которые были получены.</span><span class="sxs-lookup"><span data-stu-id="465c7-108">[out] A pointer to the number of objects that were retrieved.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="465c7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="465c7-109">Return Value</span></span>  
 <span data-ttu-id="465c7-110">Этот метод возвращает следующие специфичные результаты HRESULT.</span><span class="sxs-lookup"><span data-stu-id="465c7-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="465c7-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="465c7-111">HRESULT</span></span>|<span data-ttu-id="465c7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="465c7-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="465c7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="465c7-113">S_OK</span></span>|<span data-ttu-id="465c7-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="465c7-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="465c7-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="465c7-115">S_FALSE</span></span>|<span data-ttu-id="465c7-116">Значение параметра `pceltFetched` не равно `celt`.</span><span class="sxs-lookup"><span data-stu-id="465c7-116">`pceltFetched` does not equal `celt`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="465c7-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="465c7-117">Remarks</span></span>  
 <span data-ttu-id="465c7-118">Этот метод работает, как типичный COM-перечислитель.</span><span class="sxs-lookup"><span data-stu-id="465c7-118">This method functions like a typical COM enumerator.</span></span>  
  
 <span data-ttu-id="465c7-119">Значений входного массива должен быть не меньше размера `celt`.</span><span class="sxs-lookup"><span data-stu-id="465c7-119">The input array values must be at least of size `celt`.</span></span> <span data-ttu-id="465c7-120">Массив заполняется либо следующего `celt` значений из перечисления, либо всеми оставшимися значениями, если менее `celt` остаются.</span><span class="sxs-lookup"><span data-stu-id="465c7-120">The array will be filled with either the next `celt` values in the enumeration or with all remaining values if fewer than `celt` remain.</span></span> <span data-ttu-id="465c7-121">По возвращении из этого метода `pceltFetched` будет заполняться количество значений, которые были получены.</span><span class="sxs-lookup"><span data-stu-id="465c7-121">When this method returns, `pceltFetched` will be filled with the number of values that were retrieved.</span></span> <span data-ttu-id="465c7-122">Если `values` содержит недопустимые указатели или указывает на буфер, меньше, чем `celt`, или если `pceltFetched` является недопустимым указателем, результат будет неопределенным.</span><span class="sxs-lookup"><span data-stu-id="465c7-122">If `values` contains invalid pointers or points to a buffer that is smaller than `celt`, or if `pceltFetched` is an invalid pointer, the result is undefined.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="465c7-123">Несмотря на то что [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) необходимо освободить структуры, интерфейса «ICorDebugValue» внутри объекта необходимо освободить.</span><span class="sxs-lookup"><span data-stu-id="465c7-123">Although the [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure does not need to be released, the "ICorDebugValue" interface inside of it does need to be released.</span></span>  
  
-  
  
## <a name="requirements"></a><span data-ttu-id="465c7-124">Требования</span><span class="sxs-lookup"><span data-stu-id="465c7-124">Requirements</span></span>  
 <span data-ttu-id="465c7-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="465c7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="465c7-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="465c7-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="465c7-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="465c7-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="465c7-128">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="465c7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465c7-129">См. также</span><span class="sxs-lookup"><span data-stu-id="465c7-129">See Also</span></span>  
 [<span data-ttu-id="465c7-130">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="465c7-130">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="465c7-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="465c7-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="465c7-132">Отладка</span><span class="sxs-lookup"><span data-stu-id="465c7-132">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
