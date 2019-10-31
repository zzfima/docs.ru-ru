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
ms.openlocfilehash: e103401b85626e53db53e1894c22b161774e5163
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088689"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="fa1b8-102">Метод ICorDebugArrayValue::GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="fa1b8-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>
<span data-ttu-id="fa1b8-103">Возвращает базовый индекс каждого измерения в массиве.</span><span class="sxs-lookup"><span data-stu-id="fa1b8-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa1b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa1b8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa1b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa1b8-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="fa1b8-106">окне Число измерений данного объекта `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="fa1b8-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="fa1b8-107">Это значение также является размером массива `indicies`, так как его размер равен числу измерений объекта `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="fa1b8-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="fa1b8-108">заполняет Массив целых чисел, каждый из которых является базовым индексом (т. е. начальным индексом) измерения данного объекта `ICorDebugArrayValue`.</span><span class="sxs-lookup"><span data-stu-id="fa1b8-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa1b8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fa1b8-109">Requirements</span></span>  
 <span data-ttu-id="fa1b8-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa1b8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa1b8-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa1b8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa1b8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa1b8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa1b8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa1b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
