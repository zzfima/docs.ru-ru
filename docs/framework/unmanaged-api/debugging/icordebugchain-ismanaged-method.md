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
ms.openlocfilehash: c8c61cc12e438c0786b6e093b8bb1ea288a42e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401171"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="e2e92-102">Метод ICorDebugChain::IsManaged</span><span class="sxs-lookup"><span data-stu-id="e2e92-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="e2e92-103">Возвращает значение, указывающее, выполняется ли эта цепочка управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e2e92-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e92-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2e92-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2e92-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2e92-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="e2e92-106">[out] `true` Если эта цепочка выполняется управляемого кода; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e2e92-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e92-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e2e92-107">Requirements</span></span>  
 <span data-ttu-id="e2e92-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e92-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e92-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2e92-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2e92-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2e92-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2e92-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e92-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
