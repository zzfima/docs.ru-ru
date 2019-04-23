---
title: Метод ICorDebugModule::EnableClassLoadCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22a838748414f9d89cdc7ff469f7f5cc5e11b9d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108307"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="5d41d-102">Метод ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="5d41d-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="5d41d-103">Элементы управления ли [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) обратные вызовы, называются для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="5d41d-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d41d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d41d-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d41d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d41d-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="5d41d-106">[in] Это значение равно `true` для включения общеязыковой среды выполнения (CLR), для вызова `ICorDebugManagedCallback::LoadClass` и `ICorDebugManagedCallback::UnloadClass` методы при возникновении связанные с ними события.</span><span class="sxs-lookup"><span data-stu-id="5d41d-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="5d41d-107">Значение по умолчанию — `false` для модулей, не поддерживающих динамические.</span><span class="sxs-lookup"><span data-stu-id="5d41d-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="5d41d-108">Это значение всегда равно `true` для динамических модулей и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="5d41d-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d41d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d41d-109">Remarks</span></span>  
 <span data-ttu-id="5d41d-110">`ICorDebugManagedCallback::LoadClass` И `ICorDebugManagedCallback::UnloadClass` обратные вызовы для динамических модулей всегда включены и не может быть отключено.</span><span class="sxs-lookup"><span data-stu-id="5d41d-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d41d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5d41d-111">Requirements</span></span>  
 <span data-ttu-id="5d41d-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d41d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d41d-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d41d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d41d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d41d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d41d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d41d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d41d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5d41d-116">See also</span></span>
