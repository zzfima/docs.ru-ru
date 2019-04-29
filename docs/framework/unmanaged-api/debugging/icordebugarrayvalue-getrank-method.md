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
ms.openlocfilehash: 699c65aae205efd5b08f1d163b4ff9a223bbc217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645660"
---
# <a name="icordebugarrayvaluegetrank-method"></a><span data-ttu-id="8f2d4-102">Метод ICorDebugArrayValue::GetRank</span><span class="sxs-lookup"><span data-stu-id="8f2d4-102">ICorDebugArrayValue::GetRank Method</span></span>
<span data-ttu-id="8f2d4-103">Получает число измерений в массиве.</span><span class="sxs-lookup"><span data-stu-id="8f2d4-103">Gets the number of dimensions in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f2d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f2d4-104">Syntax</span></span>  
  
```  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f2d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f2d4-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="8f2d4-106">[out] Указатель на число измерений в этом `ICorDebugArrayValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="8f2d4-106">[out] A pointer to the number of dimensions in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f2d4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8f2d4-107">Requirements</span></span>  
 <span data-ttu-id="8f2d4-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f2d4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f2d4-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f2d4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f2d4-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f2d4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f2d4-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f2d4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
