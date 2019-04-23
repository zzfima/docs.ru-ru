---
title: Метод ICorDebugManagedCallback::CreateAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afd8bd76f8d738c9eaa3a8e3d490e175e408b92b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204306"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="fc25e-102">Метод ICorDebugManagedCallback::CreateAppDomain</span><span class="sxs-lookup"><span data-stu-id="fc25e-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="fc25e-103">Уведомляет отладчик о том, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="fc25e-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc25e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc25e-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc25e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc25e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="fc25e-106">[in] Указатель на объект ICorDebugProcess, представляющий процесс, в котором был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="fc25e-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="fc25e-107">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который был создан.</span><span class="sxs-lookup"><span data-stu-id="fc25e-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc25e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="fc25e-108">Requirements</span></span>  
 <span data-ttu-id="fc25e-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc25e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc25e-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc25e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc25e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc25e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc25e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc25e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc25e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fc25e-113">See also</span></span>

- [<span data-ttu-id="fc25e-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fc25e-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
