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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204306"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="97ec3-102">Метод ICorDebugManagedCallback::CreateAppDomain</span><span class="sxs-lookup"><span data-stu-id="97ec3-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="97ec3-103">Уведомляет отладчик о том, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="97ec3-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ec3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97ec3-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97ec3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="97ec3-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="97ec3-106">[in] Указатель на объект ICorDebugProcess, представляющий процесс, в котором был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="97ec3-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="97ec3-107">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который был создан.</span><span class="sxs-lookup"><span data-stu-id="97ec3-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ec3-108">Требования</span><span class="sxs-lookup"><span data-stu-id="97ec3-108">Requirements</span></span>  
 <span data-ttu-id="97ec3-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97ec3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ec3-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97ec3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97ec3-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97ec3-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="97ec3-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="97ec3-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97ec3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="97ec3-113">See also</span></span>

- [<span data-ttu-id="97ec3-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="97ec3-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
