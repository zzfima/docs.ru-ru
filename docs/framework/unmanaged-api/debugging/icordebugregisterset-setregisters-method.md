---
title: Метод ICorDebugRegisterSet::SetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 661225f965870d72a7b9fcb9b97906e43d6de65c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544264"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="cb49e-102">Метод ICorDebugRegisterSet::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="cb49e-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="cb49e-103">`SetRegisters` не реализуется в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="cb49e-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="cb49e-104">Этот метод не вызывается.</span><span class="sxs-lookup"><span data-stu-id="cb49e-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb49e-105">Использовать операции высокого уровня, такие как [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) или [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb49e-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb49e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb49e-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cb49e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="cb49e-107">Requirements</span></span>  
 <span data-ttu-id="cb49e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb49e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb49e-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb49e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb49e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb49e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb49e-111">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="cb49e-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb49e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cb49e-112">See also</span></span>
- [<span data-ttu-id="cb49e-113">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="cb49e-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="cb49e-114">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="cb49e-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
