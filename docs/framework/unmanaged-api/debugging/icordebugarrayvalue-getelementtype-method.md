---
title: Метод ICorDebugArrayValue::GetElementType
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementType
helpviewer_keywords:
- ICorDebugArrayValue::GetElementType method [.NET Framework debugging]
- GetElementType method [.NET Framework debugging]
ms.assetid: ed71961e-ae9b-4dfc-9554-06637696d697
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6f5f1da94e1ae07a604a616c631a38d02caea9d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496200"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="ae154-102">Метод ICorDebugArrayValue::GetElementType</span><span class="sxs-lookup"><span data-stu-id="ae154-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="ae154-103">Получает значение, указывающее простой тип элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="ae154-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae154-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae154-104">Syntax</span></span>  
  
```  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae154-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae154-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="ae154-106">[out] Указатель на значение, указывающее тип перечисления CorElementType.</span><span class="sxs-lookup"><span data-stu-id="ae154-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae154-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ae154-107">Requirements</span></span>  
 <span data-ttu-id="ae154-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae154-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae154-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae154-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae154-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae154-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae154-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae154-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
