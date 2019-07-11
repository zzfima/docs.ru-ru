---
title: Метод ICorDebugModule::IsDynamic
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db5d07d2b9a295a5cd21b4d4af954503b8bd7a8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763669"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="954c9-102">Метод ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="954c9-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="954c9-103">Получает значение, указывающее, является ли этот модуль является динамическим.</span><span class="sxs-lookup"><span data-stu-id="954c9-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="954c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="954c9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="954c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="954c9-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="954c9-106">[out] `true` Если этот модуль является динамической, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="954c9-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="954c9-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="954c9-107">Remarks</span></span>  
 <span data-ttu-id="954c9-108">Динамический модуль можно добавлять новые классы и удалять существующие классы, даже в том случае, после загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="954c9-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="954c9-109">[ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) обратные вызовы оповестить отладчик, когда добавляется или удаляется класс.</span><span class="sxs-lookup"><span data-stu-id="954c9-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="954c9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="954c9-110">Requirements</span></span>  
 <span data-ttu-id="954c9-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="954c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="954c9-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="954c9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="954c9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="954c9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="954c9-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="954c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
