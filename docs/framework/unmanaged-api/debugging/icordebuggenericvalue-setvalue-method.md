---
title: Метод ICorDebugGenericValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6907cdf78fc70c75ddd711cd8593427857b172
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756891"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="bdfa4-102">Метод ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="bdfa4-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="bdfa4-103">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="bdfa4-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfa4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdfa4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdfa4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdfa4-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="bdfa4-106">[in] Указатель на буфер, из которого необходимо скопировать значение.</span><span class="sxs-lookup"><span data-stu-id="bdfa4-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdfa4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bdfa4-107">Remarks</span></span>  
 <span data-ttu-id="bdfa4-108">Для ссылочных типов значение является ссылкой, не содержимое.</span><span class="sxs-lookup"><span data-stu-id="bdfa4-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdfa4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bdfa4-109">Requirements</span></span>  
 <span data-ttu-id="bdfa4-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdfa4-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdfa4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdfa4-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdfa4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdfa4-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdfa4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
