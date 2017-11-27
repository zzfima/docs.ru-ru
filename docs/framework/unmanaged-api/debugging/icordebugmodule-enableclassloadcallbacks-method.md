---
title: "Метод ICorDebugModule::EnableClassLoadCallbacks"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableClassLoadCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9045cceda54e6fe89c8c1baa8d4b9fa63105607
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="bf4a7-102">Метод ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="bf4a7-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="bf4a7-103">Элементы управления ли [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) , называются обратные вызовы для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="bf4a7-103">Controls whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf4a7-104">Syntax</span></span>  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf4a7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf4a7-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="bf4a7-106">[in] Это значение равно `true` для включения общеязыковой среды выполнения (CLR) для вызова `ICorDebugManagedCallback::LoadClass` и `ICorDebugManagedCallback::UnloadClass` методов при возникновении связанные с ними события.</span><span class="sxs-lookup"><span data-stu-id="bf4a7-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="bf4a7-107">Значение по умолчанию — `false` для модулей, не являющегося динамическим.</span><span class="sxs-lookup"><span data-stu-id="bf4a7-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="bf4a7-108">Это значение всегда равно `true` для динамических модулей и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="bf4a7-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf4a7-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf4a7-109">Remarks</span></span>  
 <span data-ttu-id="bf4a7-110">`ICorDebugManagedCallback::LoadClass` И `ICorDebugManagedCallback::UnloadClass` обратные вызовы всегда включена для динамических модулей и не может быть отключена.</span><span class="sxs-lookup"><span data-stu-id="bf4a7-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf4a7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bf4a7-111">Requirements</span></span>  
 <span data-ttu-id="bf4a7-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf4a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf4a7-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf4a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf4a7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf4a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf4a7-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf4a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4a7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bf4a7-116">See Also</span></span>  
    
 
