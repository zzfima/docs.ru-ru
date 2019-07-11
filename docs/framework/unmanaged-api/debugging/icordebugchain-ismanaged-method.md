---
title: Метод ICorDebugChain::IsManaged
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e14ff1cd85810a0b2f9e14c3ab4c8d12d883d17
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745619"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="2ab4b-102">Метод ICorDebugChain::IsManaged</span><span class="sxs-lookup"><span data-stu-id="2ab4b-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="2ab4b-103">Получает значение, указывающее, выполняется ли эта цепочка управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="2ab4b-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ab4b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ab4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ab4b-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="2ab4b-106">[out] `true` Если эта цепочка работает под управлением управляемого кода; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="2ab4b-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab4b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2ab4b-107">Requirements</span></span>  
 <span data-ttu-id="2ab4b-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab4b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab4b-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ab4b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ab4b-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ab4b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ab4b-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab4b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
