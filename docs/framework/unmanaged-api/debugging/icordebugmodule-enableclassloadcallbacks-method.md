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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108307"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="3bd39-102">Метод ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="3bd39-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="3bd39-103">Элементы управления ли [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) обратные вызовы, называются для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="3bd39-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bd39-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bd39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3bd39-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="3bd39-106">[in] Это значение равно `true` для включения общеязыковой среды выполнения (CLR), для вызова `ICorDebugManagedCallback::LoadClass` и `ICorDebugManagedCallback::UnloadClass` методы при возникновении связанные с ними события.</span><span class="sxs-lookup"><span data-stu-id="3bd39-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="3bd39-107">Значение по умолчанию — `false` для модулей, не поддерживающих динамические.</span><span class="sxs-lookup"><span data-stu-id="3bd39-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="3bd39-108">Это значение всегда равно `true` для динамических модулей и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="3bd39-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bd39-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3bd39-109">Remarks</span></span>  
 <span data-ttu-id="3bd39-110">`ICorDebugManagedCallback::LoadClass` И `ICorDebugManagedCallback::UnloadClass` обратные вызовы для динамических модулей всегда включены и не может быть отключено.</span><span class="sxs-lookup"><span data-stu-id="3bd39-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bd39-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3bd39-111">Requirements</span></span>  
 <span data-ttu-id="3bd39-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bd39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bd39-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bd39-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bd39-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bd39-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3bd39-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3bd39-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3bd39-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3bd39-116">See also</span></span>
