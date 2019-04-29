---
title: Метод ICorDebugArrayValue::GetElement
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElement
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElement
helpviewer_keywords:
- GetElement method [.NET Framework debugging]
- ICorDebugArrayValue::GetElement method [.NET Framework debugging]
ms.assetid: 7ac3cba5-c282-402e-b7ef-b46634f5176b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1be7eaeccb53e8b180aeb9492cd887f952bbaea5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645647"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="482f6-102">Метод ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="482f6-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="482f6-103">Получает значение заданного элемента массива.</span><span class="sxs-lookup"><span data-stu-id="482f6-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="482f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="482f6-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="482f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="482f6-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="482f6-106">[in] Размерность данного `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="482f6-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="482f6-107">Этот параметр также имеет размер `indices` массива, так как его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="482f6-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="482f6-108">[in] Массив значений индекса, каждая из которых задает позицию, в пределах измерения из `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="482f6-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="482f6-109">Это значение не может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="482f6-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="482f6-110">[out] Указатель на адрес ICorDebugValue объект, представляющий значение указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="482f6-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="482f6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="482f6-111">Requirements</span></span>  
 <span data-ttu-id="482f6-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="482f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="482f6-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="482f6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="482f6-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="482f6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="482f6-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="482f6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
