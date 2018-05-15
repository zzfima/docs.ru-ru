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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7283266857d81b7d97bcacb56862b50f01cd3f0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="cb1c8-102">Метод ICorDebugRegisterSet::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="cb1c8-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="cb1c8-103">`SetThreadContext` не реализован в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="cb1c8-104">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb1c8-105">С помощью операции более высокого уровня [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) для задания контекста потока.</span><span class="sxs-lookup"><span data-stu-id="cb1c8-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1c8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb1c8-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cb1c8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="cb1c8-107">Requirements</span></span>  
 <span data-ttu-id="cb1c8-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb1c8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb1c8-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb1c8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb1c8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb1c8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb1c8-111">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="cb1c8-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1c8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cb1c8-112">See Also</span></span>  
 [<span data-ttu-id="cb1c8-113">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="cb1c8-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="cb1c8-114">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="cb1c8-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
