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
ms.openlocfilehash: ae64fcccb49123f34cca2622a972a89bf700904f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476689"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="cf9ef-102">Метод ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="cf9ef-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="cf9ef-103">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="cf9ef-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf9ef-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf9ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cf9ef-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="cf9ef-106">[in] Указатель на буфер, из которого необходимо скопировать значение.</span><span class="sxs-lookup"><span data-stu-id="cf9ef-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf9ef-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf9ef-107">Remarks</span></span>  
 <span data-ttu-id="cf9ef-108">Для ссылочных типов значение является ссылкой, не содержимое.</span><span class="sxs-lookup"><span data-stu-id="cf9ef-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf9ef-109">Требования</span><span class="sxs-lookup"><span data-stu-id="cf9ef-109">Requirements</span></span>  
 <span data-ttu-id="cf9ef-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf9ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf9ef-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf9ef-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf9ef-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf9ef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf9ef-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf9ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
