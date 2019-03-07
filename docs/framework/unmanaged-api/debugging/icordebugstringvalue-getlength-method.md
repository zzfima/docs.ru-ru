---
title: Метод ICorDebugStringValue::GetLength
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b168673e76beddd8ae0479b8daae009c5f057b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494666"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="caf1d-102">Метод ICorDebugStringValue::GetLength</span><span class="sxs-lookup"><span data-stu-id="caf1d-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="caf1d-103">Возвращает число символов в строке, который ссылается этот ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="caf1d-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf1d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caf1d-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caf1d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="caf1d-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="caf1d-106">[out] Указатель на значение, указывающее длину строки, упоминаемой в этом `ICorDebugStringValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="caf1d-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caf1d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="caf1d-107">Requirements</span></span>  
 <span data-ttu-id="caf1d-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caf1d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf1d-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="caf1d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caf1d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caf1d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caf1d-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf1d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
