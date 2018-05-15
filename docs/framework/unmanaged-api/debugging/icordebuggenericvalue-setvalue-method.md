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
ms.openlocfilehash: 83aebad108a743d25b8ea93c99060d10bf5c3980
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="4f83b-102">Метод ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="4f83b-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="4f83b-103">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="4f83b-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f83b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f83b-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f83b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f83b-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="4f83b-106">[in] Указатель на буфер, из которого необходимо скопировать значение.</span><span class="sxs-lookup"><span data-stu-id="4f83b-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f83b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f83b-107">Remarks</span></span>  
 <span data-ttu-id="4f83b-108">Для ссылочных типов значение является ссылкой, не содержимое.</span><span class="sxs-lookup"><span data-stu-id="4f83b-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f83b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4f83b-109">Requirements</span></span>  
 <span data-ttu-id="4f83b-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f83b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f83b-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f83b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f83b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f83b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f83b-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f83b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
