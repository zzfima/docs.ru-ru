---
title: Метод ICorDebugEval::NewArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1abe307e3b9fa607912f98e456a11176eb17c56
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471515"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="f0ea8-102">Метод ICorDebugEval::NewArray</span><span class="sxs-lookup"><span data-stu-id="f0ea8-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="f0ea8-103">Выделяет новый массив элементов указанного типа и измерений.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="f0ea8-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f0ea8-105">Используйте [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ea8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0ea8-106">Syntax</span></span>  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0ea8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0ea8-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="f0ea8-108">[in] Значение перечисления CorElementType, показывающий тип элемента массива.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="f0ea8-109">[in] Указатель на объект ICorDebugClass, указывающий класс элемента.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="f0ea8-110">Это значение может иметь значение null, если тип элемента является типом-примитивом.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="f0ea8-111">[in] Число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="f0ea8-112">В .NET Framework 2.0 это значение должно быть 1.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="f0ea8-113">[in] Размер в байтах каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="f0ea8-114">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-114">[in] Optional.</span></span> <span data-ttu-id="f0ea8-115">Нижняя граница каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="f0ea8-116">Если это значение указано, для каждого измерения предполагается нижнюю границу, равную нулю.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0ea8-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0ea8-117">Remarks</span></span>  
 <span data-ttu-id="f0ea8-118">Массив всегда создается в домене приложения, в котором в настоящее время выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="f0ea8-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0ea8-119">Требования</span><span class="sxs-lookup"><span data-stu-id="f0ea8-119">Requirements</span></span>  
 <span data-ttu-id="f0ea8-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0ea8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0ea8-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0ea8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0ea8-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0ea8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0ea8-123">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="f0ea8-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
