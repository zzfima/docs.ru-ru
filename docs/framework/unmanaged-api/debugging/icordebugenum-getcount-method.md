---
title: Метод ICorDebugEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f823f660efee2d53bc1f6fa50d8878f496417379
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752275"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="9bb4d-102">Метод ICorDebugEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="9bb4d-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="9bb4d-103">Получает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="9bb4d-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bb4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bb4d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bb4d-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="9bb4d-106">[out] Указатель на число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="9bb4d-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bb4d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9bb4d-107">Requirements</span></span>  
 <span data-ttu-id="9bb4d-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bb4d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bb4d-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bb4d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bb4d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bb4d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bb4d-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bb4d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
