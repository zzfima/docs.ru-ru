---
title: Метод ICorDebugRegisterSet::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: dc2a41524d3fafe1cb45c9494d80aabe7dae0ed8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792039"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="4408d-102">Метод ICorDebugRegisterSet::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="4408d-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="4408d-103">`SetThreadContext` не реализована в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="4408d-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4408d-104">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="4408d-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4408d-105">Используйте операцию более высокого уровня [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) , чтобы задать контекст потока.</span><span class="sxs-lookup"><span data-stu-id="4408d-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4408d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4408d-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4408d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4408d-107">Requirements</span></span>  
 <span data-ttu-id="4408d-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4408d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4408d-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4408d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4408d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4408d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4408d-111">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="4408d-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4408d-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="4408d-112">See also</span></span>

- [<span data-ttu-id="4408d-113">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="4408d-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="4408d-114">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="4408d-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
