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
ms.openlocfilehash: 5a7ef478fed697f4152a6348931ddf3b4b4b2885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="dfe72-102">Метод ICorDebugManagedCallback::NameChange</span><span class="sxs-lookup"><span data-stu-id="dfe72-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="dfe72-103">Уведомляет отладчик о том, что изменилось имя домена приложения или потока.</span><span class="sxs-lookup"><span data-stu-id="dfe72-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfe72-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfe72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfe72-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="dfe72-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, было изменение имени или, содержит поток, было изменение имени.</span><span class="sxs-lookup"><span data-stu-id="dfe72-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="dfe72-107">[in] Указатель на объект ICorDebugThread, представляющий поток, было изменение имени.</span><span class="sxs-lookup"><span data-stu-id="dfe72-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfe72-108">Требования</span><span class="sxs-lookup"><span data-stu-id="dfe72-108">Requirements</span></span>  
 <span data-ttu-id="dfe72-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfe72-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe72-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfe72-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfe72-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfe72-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfe72-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe72-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe72-113">См. также</span><span class="sxs-lookup"><span data-stu-id="dfe72-113">See Also</span></span>  
 [<span data-ttu-id="dfe72-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="dfe72-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
