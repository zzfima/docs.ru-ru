---
title: Метод ICorDebugEval2::NewParameterizedArray
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c639204fa207774b0e362f1ba8fe71937494ae2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988999"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="509ce-102">Метод ICorDebugEval2::NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="509ce-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="509ce-103">Выделяет новый массив элементов указанного типа и измерений.</span><span class="sxs-lookup"><span data-stu-id="509ce-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="509ce-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="509ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="509ce-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="509ce-106">[in] Указатель на интерфейс ICorDebugType объект, представляющий тип элементов, которые хранятся в массиве.</span><span class="sxs-lookup"><span data-stu-id="509ce-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="509ce-107">[in] Число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="509ce-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="509ce-108">В платформе .NET Framework версии 2.0 это значение должно быть 1.</span><span class="sxs-lookup"><span data-stu-id="509ce-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="509ce-109">[in] Размер в байтах каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="509ce-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="509ce-110">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="509ce-110">[in] Optional.</span></span> <span data-ttu-id="509ce-111">Нижняя граница каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="509ce-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="509ce-112">Если это значение указано, для каждого измерения предполагается нижнюю границу, равную нулю.</span><span class="sxs-lookup"><span data-stu-id="509ce-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="509ce-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="509ce-113">Remarks</span></span>  
 <span data-ttu-id="509ce-114">Элементы массива могут быть экземпляры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="509ce-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="509ce-115">Массив всегда создается в домене приложения, в котором поток выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="509ce-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="509ce-116">В .NET Framework 2.0, значение `rank` должно быть равно 1.</span><span class="sxs-lookup"><span data-stu-id="509ce-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="509ce-117">Требования</span><span class="sxs-lookup"><span data-stu-id="509ce-117">Requirements</span></span>  
 <span data-ttu-id="509ce-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="509ce-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="509ce-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="509ce-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="509ce-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="509ce-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="509ce-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="509ce-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
