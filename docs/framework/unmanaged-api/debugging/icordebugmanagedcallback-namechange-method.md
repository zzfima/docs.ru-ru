---
title: Метод ICorDebugManagedCallback::NameChange
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8bc4eb1895fe67c25354b42fe3ae1ffe80bca58
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491325"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="4e574-102">Метод ICorDebugManagedCallback::NameChange</span><span class="sxs-lookup"><span data-stu-id="4e574-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="4e574-103">Уведомляет отладчик о том, что имя домена приложения или поток был изменен.</span><span class="sxs-lookup"><span data-stu-id="4e574-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e574-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e574-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e574-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e574-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4e574-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, которое было изменение имени или, содержит поток, в котором произошло изменение имени.</span><span class="sxs-lookup"><span data-stu-id="4e574-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4e574-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором произошло изменение имени.</span><span class="sxs-lookup"><span data-stu-id="4e574-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e574-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4e574-108">Requirements</span></span>  
 <span data-ttu-id="4e574-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e574-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e574-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e574-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e574-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e574-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e574-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e574-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e574-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4e574-113">See also</span></span>
- [<span data-ttu-id="4e574-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="4e574-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
