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
ms.openlocfilehash: 8e0159ce6ad1087838681214533d386f4d44cee2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737470"
---
# <a name="icordebugarrayvaluegetelementtype-method"></a><span data-ttu-id="d1826-102">Метод ICorDebugArrayValue::GetElementType</span><span class="sxs-lookup"><span data-stu-id="d1826-102">ICorDebugArrayValue::GetElementType Method</span></span>
<span data-ttu-id="d1826-103">Получает значение, указывающее простой тип элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="d1826-103">Gets a value that indicates the simple type of the elements in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1826-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1826-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementType (  
    [out] CorElementType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1826-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1826-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="d1826-106">[out] Указатель на значение, указывающее тип перечисления CorElementType.</span><span class="sxs-lookup"><span data-stu-id="d1826-106">[out] A pointer to a value of the CorElementType enumeration that indicates the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1826-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d1826-107">Requirements</span></span>  
 <span data-ttu-id="d1826-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1826-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1826-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1826-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1826-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1826-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1826-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1826-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
