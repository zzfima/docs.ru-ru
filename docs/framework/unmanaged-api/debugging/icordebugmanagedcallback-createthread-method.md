---
title: "Метод ICorDebugManagedCallback::CreateThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8acb12d216949fc4e0636b5a2c28657ef5c79bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="49764-102">Метод ICorDebugManagedCallback::CreateThread</span><span class="sxs-lookup"><span data-stu-id="49764-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="49764-103">Уведомляет отладчик о том, что поток начал выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="49764-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49764-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49764-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49764-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49764-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="49764-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который содержит поток.</span><span class="sxs-lookup"><span data-stu-id="49764-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="49764-107">[in] Указатель на объект ICorDebugThread, представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="49764-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49764-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="49764-108">Remarks</span></span>  
 <span data-ttu-id="49764-109">Поток будет расположен в первой инструкции для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="49764-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49764-110">Требования</span><span class="sxs-lookup"><span data-stu-id="49764-110">Requirements</span></span>  
 <span data-ttu-id="49764-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49764-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49764-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49764-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49764-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49764-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49764-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49764-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49764-115">См. также</span><span class="sxs-lookup"><span data-stu-id="49764-115">See Also</span></span>  
 [<span data-ttu-id="49764-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="49764-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
