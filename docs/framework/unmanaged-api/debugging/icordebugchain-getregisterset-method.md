---
title: Метод ICorDebugChain::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f366a40e1e3cd196f480c5849c49419c7daeea9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989486"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="12175-102">Метод ICorDebugChain::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="12175-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="12175-103">Получает набор регистров для активной части этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="12175-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12175-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12175-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12175-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12175-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="12175-106">[out] Указатель на адрес [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , представляющий регистра задать для активной части этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="12175-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12175-107">Требования</span><span class="sxs-lookup"><span data-stu-id="12175-107">Requirements</span></span>  
 <span data-ttu-id="12175-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12175-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12175-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12175-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12175-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12175-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12175-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12175-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
