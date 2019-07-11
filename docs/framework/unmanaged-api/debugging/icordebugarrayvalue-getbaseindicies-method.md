---
title: Метод ICorDebugArrayValue::GetBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f4ecb700a19a4e06f9f0056881fe3cdb9753aae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737607"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="f14b1-102">Метод ICorDebugArrayValue::GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="f14b1-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="f14b1-103">Получает базовый индекс каждого измерения в массиве.</span><span class="sxs-lookup"><span data-stu-id="f14b1-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f14b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f14b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f14b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f14b1-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="f14b1-106">[in] Размерность данного `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="f14b1-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="f14b1-107">Этот параметр также имеет размер `indicies` массива, так как его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="f14b1-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="f14b1-108">[out] Массив целых чисел, каждое из которых является базовый индекс (то есть, начальный индекс) измерения данного `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="f14b1-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f14b1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f14b1-109">Requirements</span></span>  
 <span data-ttu-id="f14b1-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f14b1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f14b1-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f14b1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f14b1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f14b1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f14b1-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f14b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
