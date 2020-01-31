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
ms.openlocfilehash: d61d37448930d451b519c93909165e5e16f92765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792054"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="3cde3-102">Метод ICorDebugRegisterSet::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="3cde3-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="3cde3-103">`SetRegisters` не реализована в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="3cde3-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="3cde3-104">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="3cde3-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cde3-105">Используйте операции более высокого уровня, такие как [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) или [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="3cde3-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cde3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cde3-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3cde3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3cde3-107">Requirements</span></span>  
 <span data-ttu-id="3cde3-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cde3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cde3-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cde3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cde3-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cde3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cde3-111">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="3cde3-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cde3-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="3cde3-112">See also</span></span>

- [<span data-ttu-id="3cde3-113">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="3cde3-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="3cde3-114">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="3cde3-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
