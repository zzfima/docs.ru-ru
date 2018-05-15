---
title: Метод ICorDebugManagedCallback::UnloadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ca9ed57e62d2c066de2d7c1a1e4b57094dbc0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="dd87e-102">Метод ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="dd87e-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="dd87e-103">Уведомляет отладчик о выгрузке общих модуля среды CLR (DLL).</span><span class="sxs-lookup"><span data-stu-id="dd87e-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd87e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd87e-104">Syntax</span></span>  
  
```  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd87e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd87e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="dd87e-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который содержится в модуле.</span><span class="sxs-lookup"><span data-stu-id="dd87e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="dd87e-107">[in] Указатель на объект ICorDebugModule, представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="dd87e-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd87e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd87e-108">Remarks</span></span>  
 <span data-ttu-id="dd87e-109">После этого вызова не следует использовать модуль.</span><span class="sxs-lookup"><span data-stu-id="dd87e-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd87e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dd87e-110">Requirements</span></span>  
 <span data-ttu-id="dd87e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd87e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd87e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd87e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd87e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd87e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd87e-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd87e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd87e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dd87e-115">See Also</span></span>  
 [<span data-ttu-id="dd87e-116">Метод LoadModule</span><span class="sxs-lookup"><span data-stu-id="dd87e-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)  
 [<span data-ttu-id="dd87e-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="dd87e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
