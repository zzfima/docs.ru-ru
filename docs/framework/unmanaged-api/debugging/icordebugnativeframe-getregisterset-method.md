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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987874"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="b04c7-102">Метод ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="b04c7-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="b04c7-103">Получает набор регистров для этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="b04c7-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b04c7-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b04c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b04c7-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="b04c7-106">[out] Указатель на адрес [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , представляющий регистра задать для этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="b04c7-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b04c7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b04c7-107">Requirements</span></span>  
 <span data-ttu-id="b04c7-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b04c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b04c7-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b04c7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b04c7-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b04c7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b04c7-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b04c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04c7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b04c7-112">See also</span></span>
