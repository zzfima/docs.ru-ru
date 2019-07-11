---
title: Метод ICorDebugRegisterSet2::SetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e11e7eb477d938d3ccba352ef357d927af966bc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770657"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="63747-102">Метод ICorDebugRegisterSet2::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="63747-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="63747-103">`SetRegisters` не реализуется в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="63747-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="63747-104">Этот метод не вызывается.</span><span class="sxs-lookup"><span data-stu-id="63747-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63747-105">Использовать операции высокого уровня, такие как [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) или [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="63747-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63747-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63747-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="63747-107">Требования</span><span class="sxs-lookup"><span data-stu-id="63747-107">Requirements</span></span>  
 <span data-ttu-id="63747-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63747-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63747-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63747-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63747-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63747-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63747-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63747-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63747-112">См. также</span><span class="sxs-lookup"><span data-stu-id="63747-112">See also</span></span>

- [<span data-ttu-id="63747-113">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="63747-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="63747-114">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="63747-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
