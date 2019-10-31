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
ms.openlocfilehash: ca0844e4d2b1cad65266d58c6cda74de203d1758
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137663"
---
# <a name="icordebugevalnewarray-method"></a><span data-ttu-id="ca04c-102">Метод ICorDebugEval::NewArray</span><span class="sxs-lookup"><span data-stu-id="ca04c-102">ICorDebugEval::NewArray Method</span></span>
<span data-ttu-id="ca04c-103">Выделяет новый массив указанного типа элемента и измерений.</span><span class="sxs-lookup"><span data-stu-id="ca04c-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
 <span data-ttu-id="ca04c-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="ca04c-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ca04c-105">Вместо этого используйте [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ca04c-105">Use [ICorDebugEval2::NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca04c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca04c-106">Syntax</span></span>  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca04c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca04c-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="ca04c-108">окне Значение перечисления Корелементтипе, указывающее тип элемента массива.</span><span class="sxs-lookup"><span data-stu-id="ca04c-108">[in] A value of the CorElementType enumeration that specifies the element type of the array.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="ca04c-109">окне Указатель на объект ICorDebugClass, указывающий класс элемента.</span><span class="sxs-lookup"><span data-stu-id="ca04c-109">[in] A pointer to a ICorDebugClass object that specifies the class of the element.</span></span> <span data-ttu-id="ca04c-110">Это значение может быть равно null, если тип элемента является типом-примитивом.</span><span class="sxs-lookup"><span data-stu-id="ca04c-110">This value may be null if the element type is a primitive type.</span></span>  
  
 `rank`  
 <span data-ttu-id="ca04c-111">окне Число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="ca04c-111">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="ca04c-112">В .NET Framework 2,0 это значение должно быть равно 1.</span><span class="sxs-lookup"><span data-stu-id="ca04c-112">In the .NET Framework 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="ca04c-113">окне Размер каждого измерения массива в байтах.</span><span class="sxs-lookup"><span data-stu-id="ca04c-113">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="ca04c-114">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="ca04c-114">[in] Optional.</span></span> <span data-ttu-id="ca04c-115">Нижняя граница каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="ca04c-115">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="ca04c-116">Если это значение пропущено, для каждого измерения предполагается Нижняя граница, равная нулю.</span><span class="sxs-lookup"><span data-stu-id="ca04c-116">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca04c-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="ca04c-117">Remarks</span></span>  
 <span data-ttu-id="ca04c-118">Массив всегда создается в домене приложения, в котором в данный момент выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="ca04c-118">The array is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca04c-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ca04c-119">Requirements</span></span>  
 <span data-ttu-id="ca04c-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca04c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca04c-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca04c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca04c-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca04c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca04c-123">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="ca04c-123">**.NET Framework Versions:** 1.1, 1.0</span></span>
