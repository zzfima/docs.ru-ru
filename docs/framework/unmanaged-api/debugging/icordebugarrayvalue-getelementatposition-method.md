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
ms.openlocfilehash: 10584442d7e0bd61e6decaf2b494dfe39f339d6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088420"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="359cb-102">Метод ICorDebugArrayValue::GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="359cb-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>
<span data-ttu-id="359cb-103">Возвращает элемент в заданной позиции, рассматривая массив как одномерный массив с отсчетом от нуля.</span><span class="sxs-lookup"><span data-stu-id="359cb-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="359cb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="359cb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="359cb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="359cb-105">Parameters</span></span>  
 `nPosition`  
 <span data-ttu-id="359cb-106">окне Расположение извлекаемого элемента.</span><span class="sxs-lookup"><span data-stu-id="359cb-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="359cb-107">заполняет Указатель на адрес объекта ICorDebugValue, который представляет значение элемента.</span><span class="sxs-lookup"><span data-stu-id="359cb-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="359cb-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="359cb-108">Remarks</span></span>  
 <span data-ttu-id="359cb-109">Макет массива с несколькими измерениями соответствует C++ стилю макета массива.</span><span class="sxs-lookup"><span data-stu-id="359cb-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="359cb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="359cb-110">Requirements</span></span>  
 <span data-ttu-id="359cb-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="359cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="359cb-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="359cb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="359cb-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="359cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="359cb-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="359cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
