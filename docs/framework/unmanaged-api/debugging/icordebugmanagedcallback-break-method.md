---
title: Метод ICorDebugManagedCallback::Break
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7120e092b422b755ecbde9e48236b42e67636fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414942"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="9680a-102">Метод ICorDebugManagedCallback::Break</span><span class="sxs-lookup"><span data-stu-id="9680a-102">ICorDebugManagedCallback::Break Method</span></span>
<span data-ttu-id="9680a-103">Уведомляет отладчик при <xref:System.Reflection.Emit.OpCodes.Break> инструкции в поток кода.</span><span class="sxs-lookup"><span data-stu-id="9680a-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9680a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9680a-104">Syntax</span></span>  
  
```  
HRESULT Break (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9680a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9680a-105">Parameters</span></span>  
 `pAppDOmain`  
 <span data-ttu-id="9680a-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который содержит инструкцию break.</span><span class="sxs-lookup"><span data-stu-id="9680a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>  
  
 `thread`  
 <span data-ttu-id="9680a-107">[in] Указатель на объект ICorDebugThread, представляющий поток, содержащий инструкцию break.</span><span class="sxs-lookup"><span data-stu-id="9680a-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9680a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9680a-108">Requirements</span></span>  
 <span data-ttu-id="9680a-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9680a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9680a-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9680a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9680a-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9680a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9680a-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9680a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9680a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9680a-113">See Also</span></span>  
 [<span data-ttu-id="9680a-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9680a-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
