---
title: "Метод ICorDebugModule::IsDynamic"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.IsDynamic
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3583749ddb48015b43d45061d3e4cb10e08016b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="12d39-102">Метод ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="12d39-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="12d39-103">Возвращает значение, указывающее, является ли этот модуль является динамическим.</span><span class="sxs-lookup"><span data-stu-id="12d39-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12d39-104">Syntax</span></span>  
  
```  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12d39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12d39-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="12d39-106">[out] `true` Если этот модуль является динамической, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="12d39-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12d39-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="12d39-107">Remarks</span></span>  
 <span data-ttu-id="12d39-108">Динамический модуль может добавлять новые классы и удалять существующие классы даже после загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="12d39-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="12d39-109">[ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) обратные вызовы оповестить отладчик, когда добавляется или удаляется класс.</span><span class="sxs-lookup"><span data-stu-id="12d39-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12d39-110">Требования</span><span class="sxs-lookup"><span data-stu-id="12d39-110">Requirements</span></span>  
 <span data-ttu-id="12d39-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12d39-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12d39-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12d39-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12d39-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12d39-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12d39-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12d39-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
