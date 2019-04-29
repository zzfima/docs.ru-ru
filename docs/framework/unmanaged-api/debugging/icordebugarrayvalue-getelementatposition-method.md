---
title: Метод ICorDebugArrayValue::GetElementAtPosition
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76100116f2ca3a9b9a99477ca2352d5fa1335ab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645686"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="d13f1-102">Метод ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="d13f1-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="d13f1-103">Получает элемент в заданной позиции, обработка массива в виде — отсчитываемый от нуля одномерный массив.</span><span class="sxs-lookup"><span data-stu-id="d13f1-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d13f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d13f1-104">Syntax</span></span>  
  
```  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d13f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d13f1-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="d13f1-106">[in] Позиция элемента, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="d13f1-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d13f1-107">[out] Указатель на адрес объекта ICorDebugValue, который представляет значение элемента.</span><span class="sxs-lookup"><span data-stu-id="d13f1-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d13f1-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d13f1-108">Remarks</span></span>  
 <span data-ttu-id="d13f1-109">Макет многомерного массива следует C++ стиль макета массива.</span><span class="sxs-lookup"><span data-stu-id="d13f1-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d13f1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d13f1-110">Requirements</span></span>  
 <span data-ttu-id="d13f1-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d13f1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d13f1-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d13f1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d13f1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d13f1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d13f1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d13f1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
