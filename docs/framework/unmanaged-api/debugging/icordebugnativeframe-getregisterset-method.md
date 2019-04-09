---
title: Метод ICorDebugNativeFrame::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03a4f7ecc227679e6b0afa29b20de1aefeae3b76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077931"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="92d31-102">Метод ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="92d31-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="92d31-103">Получает набор регистров для этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="92d31-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92d31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92d31-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92d31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92d31-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="92d31-106">[out] Указатель на адрес [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , представляющий регистра задать для этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="92d31-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92d31-107">Требования</span><span class="sxs-lookup"><span data-stu-id="92d31-107">Requirements</span></span>  
 <span data-ttu-id="92d31-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92d31-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92d31-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92d31-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92d31-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92d31-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="92d31-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="92d31-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="92d31-112">См. также</span><span class="sxs-lookup"><span data-stu-id="92d31-112">See also</span></span>
