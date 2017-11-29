---
title: "ICorDebugArrayValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13e226ccdcd6becc98d524c429b5cadae8d19c3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvalue-interface1"></a><span data-ttu-id="4b997-102">ICorDebugArrayValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="4b997-102">ICorDebugArrayValue Interface1</span></span>
<span data-ttu-id="4b997-103">Подкласс ICorDebugHeapValue, представляющий одномерный или многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="4b997-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b997-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4b997-104">Methods</span></span>  
  
|<span data-ttu-id="4b997-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4b997-105">Method</span></span>|<span data-ttu-id="4b997-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4b997-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b997-107">Метод GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="4b997-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="4b997-108">Получает базовый индекс каждого измерения в массиве.</span><span class="sxs-lookup"><span data-stu-id="4b997-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="4b997-109">GetCount-метод</span><span class="sxs-lookup"><span data-stu-id="4b997-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="4b997-110">Получает общее число элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="4b997-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="4b997-111">Метод GetDimensions</span><span class="sxs-lookup"><span data-stu-id="4b997-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="4b997-112">Возвращает размерность массива.</span><span class="sxs-lookup"><span data-stu-id="4b997-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="4b997-113">GetElement-метод</span><span class="sxs-lookup"><span data-stu-id="4b997-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="4b997-114">Возвращает значение, представляющее данный элемент в массиве.</span><span class="sxs-lookup"><span data-stu-id="4b997-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="4b997-115">Метод GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="4b997-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="4b997-116">Возвращает элемент в заданной позиции, обработке массива как отсчитываемый от нуля одномерный массив.</span><span class="sxs-lookup"><span data-stu-id="4b997-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="4b997-117">Метод GetElementType</span><span class="sxs-lookup"><span data-stu-id="4b997-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="4b997-118">Получает простой тип элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="4b997-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="4b997-119">Метод GetRank</span><span class="sxs-lookup"><span data-stu-id="4b997-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="4b997-120">Получает число измерений в массиве.</span><span class="sxs-lookup"><span data-stu-id="4b997-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="4b997-121">Метод HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="4b997-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="4b997-122">Определяет, имеет ли массив базовые индексы.</span><span class="sxs-lookup"><span data-stu-id="4b997-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b997-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b997-123">Remarks</span></span>  
 <span data-ttu-id="4b997-124">`ICorDebugArrayValue`поддерживает одномерные и многомерные массивы.</span><span class="sxs-lookup"><span data-stu-id="4b997-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b997-125">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4b997-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b997-126">Требования</span><span class="sxs-lookup"><span data-stu-id="4b997-126">Requirements</span></span>  
 <span data-ttu-id="4b997-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b997-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b997-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b997-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b997-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b997-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b997-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b997-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b997-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4b997-131">See Also</span></span>  
 [<span data-ttu-id="4b997-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4b997-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
