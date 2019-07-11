---
title: Метод ICorDebugManagedCallback::ExitAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1e045c475b57f863071eb81194868b7db3c5a3c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755798"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="7f6a8-102">Метод ICorDebugManagedCallback::ExitAppDomain</span><span class="sxs-lookup"><span data-stu-id="7f6a8-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="7f6a8-103">Уведомляет отладчик о том, что завершил работу домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7f6a8-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f6a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f6a8-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f6a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f6a8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7f6a8-106">[in] Указатель на объект ICorDebugProcess, представляющий процесс, содержащий указанный домен приложения.</span><span class="sxs-lookup"><span data-stu-id="7f6a8-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="7f6a8-107">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который завершил работу.</span><span class="sxs-lookup"><span data-stu-id="7f6a8-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f6a8-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7f6a8-108">Requirements</span></span>  
 <span data-ttu-id="7f6a8-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f6a8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f6a8-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f6a8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f6a8-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f6a8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f6a8-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f6a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f6a8-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7f6a8-113">See also</span></span>

- [<span data-ttu-id="7f6a8-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7f6a8-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
