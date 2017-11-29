---
title: "Метод ICorDebugRegisterSet::SetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a97706e5cf407f16b6d06efce11576fbb131d1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="ddb44-102">Метод ICorDebugRegisterSet::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="ddb44-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="ddb44-103">`SetThreadContext`не реализован в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="ddb44-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ddb44-104">Не вызывайте этот метод.</span><span class="sxs-lookup"><span data-stu-id="ddb44-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddb44-105">С помощью операции более высокого уровня [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) для задания контекста потока.</span><span class="sxs-lookup"><span data-stu-id="ddb44-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddb44-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddb44-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ddb44-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ddb44-107">Requirements</span></span>  
 <span data-ttu-id="ddb44-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddb44-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddb44-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddb44-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddb44-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddb44-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddb44-111">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ddb44-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb44-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ddb44-112">See Also</span></span>  
 [<span data-ttu-id="ddb44-113">ICorDebugRegisterSet-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ddb44-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="ddb44-114">ICorDebugRegisterSet2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ddb44-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
