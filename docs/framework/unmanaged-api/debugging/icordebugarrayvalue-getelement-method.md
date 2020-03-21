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
ms.openlocfilehash: adcb7b5a27f3b8c63dbbb660a23b5c891f84ac46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179012"
---
# <a name="icordebugarrayvaluegetelement-method"></a><span data-ttu-id="17849-102">Метод ICorDebugArrayValue::GetElement</span><span class="sxs-lookup"><span data-stu-id="17849-102">ICorDebugArrayValue::GetElement Method</span></span>
<span data-ttu-id="17849-103">Получает значение данного элемента массива.</span><span class="sxs-lookup"><span data-stu-id="17849-103">Gets the value of the given array element.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17849-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17849-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElement (  
    [in]  ULONG32          cdim,  
    [in, size_is(cdim), length_is(cdim)]
         ULONG32           indices[],  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17849-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="17849-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="17849-106">(в) Количество размеров этого `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="17849-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="17849-107">Это значение также является `indices` размером массива, поскольку его размер `ICorDebugArrayValue` равен количеству размеров объекта.</span><span class="sxs-lookup"><span data-stu-id="17849-107">This value is also the size of the `indices` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indices`  
 <span data-ttu-id="17849-108">(в) Массив значений индекса, каждое из которых определяет положение в `ICorDebugArrayValue` измерении объекта.</span><span class="sxs-lookup"><span data-stu-id="17849-108">[in] An array of index values, each of which specifies a position within a dimension of the `ICorDebugArrayValue` object.</span></span>  
  
 <span data-ttu-id="17849-109">Это значение не должно быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="17849-109">This value must not be null.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="17849-110">(ваут) Указатель на адрес объекта ICorDebugValue, представляющий значение указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="17849-110">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified element.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17849-111">Требования</span><span class="sxs-lookup"><span data-stu-id="17849-111">Requirements</span></span>  
 <span data-ttu-id="17849-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17849-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17849-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17849-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17849-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17849-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17849-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17849-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
