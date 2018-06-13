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
ms.openlocfilehash: 500e01955666c7a8e2bd1dcf9d34afe3aeb6b421
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403348"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="6209d-102">Метод ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="6209d-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="6209d-103">Получает значение заданного элемента массива.</span><span class="sxs-lookup"><span data-stu-id="6209d-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6209d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6209d-104">Syntax</span></span>  
  
```  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]   
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6209d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6209d-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="6209d-106">[in] Размерность этого `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="6209d-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="6209d-107">Этот параметр также имеет размер `indices` массива, так как его размер равен числу измерений `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="6209d-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="6209d-108">[in] Массив значений индекса, каждая из которых задает измерение, позиция в массиве `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="6209d-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="6209d-109">Это значение не может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="6209d-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6209d-110">[out] Указатель на адрес объекта ICorDebugValue, представляющее значение указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="6209d-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6209d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6209d-111">Requirements</span></span>  
 <span data-ttu-id="6209d-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6209d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6209d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6209d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6209d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6209d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6209d-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6209d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
