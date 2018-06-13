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
ms.openlocfilehash: 552d2fa8a7c35066e32fb9f8e9455b3092b1e65b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413284"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="2531f-102">Метод ICorDebugEval2::NewParameterizedArray</span><span class="sxs-lookup"><span data-stu-id="2531f-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="2531f-103">Выделяет новый массив с заданным типом элементов и измерений.</span><span class="sxs-lookup"><span data-stu-id="2531f-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2531f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2531f-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2531f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2531f-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="2531f-106">[in] Указатель на объект ICorDebugType, представляющий тип элементов, которые хранятся в массиве.</span><span class="sxs-lookup"><span data-stu-id="2531f-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="2531f-107">[in] Число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="2531f-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="2531f-108">В платформе .NET Framework версии 2.0 это значение должно быть 1.</span><span class="sxs-lookup"><span data-stu-id="2531f-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="2531f-109">[in] Размер в байтах для каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="2531f-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="2531f-110">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="2531f-110">[in] Optional.</span></span> <span data-ttu-id="2531f-111">Нижняя граница каждого измерения массива.</span><span class="sxs-lookup"><span data-stu-id="2531f-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="2531f-112">Если это значение указано, для каждого измерения предполагается нижнюю границу, равную нулю.</span><span class="sxs-lookup"><span data-stu-id="2531f-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2531f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="2531f-113">Remarks</span></span>  
 <span data-ttu-id="2531f-114">Элементы массива могут быть экземпляры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="2531f-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="2531f-115">Массив всегда создается в домене приложения, в котором в настоящее время выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="2531f-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="2531f-116">В .NET Framework версии 2.0 значение `rank` должно иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="2531f-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2531f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2531f-117">Requirements</span></span>  
 <span data-ttu-id="2531f-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2531f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2531f-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2531f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2531f-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2531f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2531f-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2531f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
