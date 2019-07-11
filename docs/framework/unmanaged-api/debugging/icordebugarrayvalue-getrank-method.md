---
title: Метод ICorDebugArrayValue::GetRank
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetRank
helpviewer_keywords:
- ICorDebugArrayValue::GetRank method [.NET Framework debugging]
- GetRank method, ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: 5e83c82c-593d-4691-90b0-383d218b415e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abf24b81bae4d16c3a03aa668d4e1f5e8117cc93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737463"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="bc055-102">Метод ICorDebugArrayValue::GetRank</span><span class="sxs-lookup"><span data-stu-id="bc055-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="bc055-103">Получает число измерений в массиве.</span><span class="sxs-lookup"><span data-stu-id="bc055-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc055-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc055-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc055-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc055-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="bc055-106">[out] Указатель на число измерений в этом `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="bc055-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc055-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bc055-107">Requirements</span></span>  
 <span data-ttu-id="bc055-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc055-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc055-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc055-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc055-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc055-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc055-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc055-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
