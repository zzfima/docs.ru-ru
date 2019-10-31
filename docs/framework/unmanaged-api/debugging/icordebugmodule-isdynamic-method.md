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
ms.openlocfilehash: 5774b40178ce0d7c2ef5d063a37b9011fc2630df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127952"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="da0d4-102">Метод ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="da0d4-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="da0d4-103">Возвращает значение, указывающее, является ли этот модуль динамическим.</span><span class="sxs-lookup"><span data-stu-id="da0d4-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da0d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da0d4-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da0d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="da0d4-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="da0d4-106">[out] `true`, если этот модуль является динамическим; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="da0d4-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da0d4-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="da0d4-107">Remarks</span></span>  
 <span data-ttu-id="da0d4-108">Динамический модуль может добавлять новые классы и удалять существующие классы даже после загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="da0d4-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="da0d4-109">Обратные вызовы [ICorDebugManagedCallback:: loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) информируют отладчик о добавлении или удалении класса.</span><span class="sxs-lookup"><span data-stu-id="da0d4-109">The [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da0d4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="da0d4-110">Requirements</span></span>  
 <span data-ttu-id="da0d4-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da0d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da0d4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da0d4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da0d4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da0d4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da0d4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da0d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
