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
ms.openlocfilehash: 45b1d0c0a3199227ab644ba8732198dd14b1cb4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792998"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="ab251-102">Метод ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="ab251-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="ab251-103">Возвращает значение, указывающее, является ли этот модуль динамическим.</span><span class="sxs-lookup"><span data-stu-id="ab251-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab251-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab251-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab251-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab251-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="ab251-106">[out] `true`, если этот модуль является динамическим; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="ab251-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab251-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="ab251-107">Remarks</span></span>  
 <span data-ttu-id="ab251-108">Динамический модуль может добавлять новые классы и удалять существующие классы даже после загрузки модуля.</span><span class="sxs-lookup"><span data-stu-id="ab251-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="ab251-109">Обратные вызовы [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](icordebugmanagedcallback-unloadclass-method.md) информируют отладчик о добавлении или удалении класса.</span><span class="sxs-lookup"><span data-stu-id="ab251-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab251-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ab251-110">Requirements</span></span>  
 <span data-ttu-id="ab251-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab251-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab251-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab251-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab251-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab251-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab251-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab251-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
