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
ms.openlocfilehash: bdac4b5b7a4a64a5fc939a7d35718ef276717fe7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="907d4-102">Метод ICorDebugManagedCallback::CreateAppDomain</span><span class="sxs-lookup"><span data-stu-id="907d4-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="907d4-103">Уведомляет отладчик, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="907d4-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="907d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="907d4-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="907d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="907d4-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="907d4-106">[in] Указатель на объект ICorDebugProcess, представляет собой процесс, в которой был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="907d4-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="907d4-107">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который был создан.</span><span class="sxs-lookup"><span data-stu-id="907d4-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="907d4-108">Требования</span><span class="sxs-lookup"><span data-stu-id="907d4-108">Requirements</span></span>  
 <span data-ttu-id="907d4-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="907d4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="907d4-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="907d4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="907d4-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="907d4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="907d4-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="907d4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907d4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="907d4-113">See Also</span></span>  
 [<span data-ttu-id="907d4-114">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="907d4-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
