---
title: "Метод ICorDebugManagedCallback::UnloadModule"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7aeb3f12d5217c57d8d8f1f5665840a4515c0998
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="9cefc-102">Метод ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="9cefc-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="9cefc-103">Уведомляет отладчик о выгрузке общих модуля среды CLR (DLL).</span><span class="sxs-lookup"><span data-stu-id="9cefc-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cefc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cefc-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cefc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cefc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9cefc-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который содержится в модуле.</span><span class="sxs-lookup"><span data-stu-id="9cefc-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="9cefc-107">[in] Указатель на объект ICorDebugModule, представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="9cefc-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cefc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cefc-108">Remarks</span></span>  
 <span data-ttu-id="9cefc-109">После этого вызова не следует использовать модуль.</span><span class="sxs-lookup"><span data-stu-id="9cefc-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cefc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9cefc-110">Requirements</span></span>  
 <span data-ttu-id="9cefc-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cefc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cefc-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cefc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cefc-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cefc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cefc-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cefc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cefc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9cefc-115">See Also</span></span>  
 [<span data-ttu-id="9cefc-116">Метод LoadModule</span><span class="sxs-lookup"><span data-stu-id="9cefc-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)  
 [<span data-ttu-id="9cefc-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9cefc-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
