---
title: Метод ICorDebugManagedCallback::LoadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8fde6772a43cc763df82ec109c11f8548ba240e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476182"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="d3b4a-102">Метод ICorDebugManagedCallback::LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="d3b4a-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="d3b4a-103">Уведомляет отладчик, что сборки среды выполнения (CLR) CLR была успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3b4a-104">Syntax</span></span>  
  
```  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3b4a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3b4a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d3b4a-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в который была загружена сборка.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="d3b4a-107">[in] Указатель на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="d3b4a-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3b4a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d3b4a-108">Requirements</span></span>  
 <span data-ttu-id="d3b4a-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3b4a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3b4a-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3b4a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3b4a-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3b4a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3b4a-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3b4a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b4a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d3b4a-113">See also</span></span>
- [<span data-ttu-id="d3b4a-114">Метод UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="d3b4a-114">UnloadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="d3b4a-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d3b4a-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
