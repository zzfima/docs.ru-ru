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
ms.openlocfilehash: d552b694787b5d9f0d5adc399eda6f75df93c385
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793025"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a><span data-ttu-id="b225f-102">Метод ICorDebugModule::EnableClassLoadCallbacks</span><span class="sxs-lookup"><span data-stu-id="b225f-102">ICorDebugModule::EnableClassLoadCallbacks Method</span></span>
<span data-ttu-id="b225f-103">Определяет, вызываются ли для этого модуля обратные вызовы [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](icordebugmanagedcallback-unloadclass-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b225f-103">Controls whether the [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b225f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b225f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b225f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b225f-105">Parameters</span></span>  
 `bClassLoadCallbacks`  
 <span data-ttu-id="b225f-106">окне Присвойте этому параметру значение `true`, чтобы среда CLR вызывала методы `ICorDebugManagedCallback::LoadClass` и `ICorDebugManagedCallback::UnloadClass` при возникновении связанных с ними событий.</span><span class="sxs-lookup"><span data-stu-id="b225f-106">[in] Set this value to `true` to enable the common language runtime (CLR) to call the `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` methods when their associated events occur.</span></span>  
  
 <span data-ttu-id="b225f-107">Значение по умолчанию — `false` для модулей, не являющихся динамическими.</span><span class="sxs-lookup"><span data-stu-id="b225f-107">The default value is `false` for non-dynamic modules.</span></span> <span data-ttu-id="b225f-108">Значение всегда `true` для динамических модулей и не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="b225f-108">The value is always `true` for dynamic modules and cannot be changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b225f-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="b225f-109">Remarks</span></span>  
 <span data-ttu-id="b225f-110">Обратные вызовы `ICorDebugManagedCallback::LoadClass` и `ICorDebugManagedCallback::UnloadClass` всегда включены для динамических модулей и не могут быть отключены.</span><span class="sxs-lookup"><span data-stu-id="b225f-110">The `ICorDebugManagedCallback::LoadClass` and `ICorDebugManagedCallback::UnloadClass` callbacks are always enabled for dynamic modules and cannot be disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b225f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b225f-111">Requirements</span></span>  
 <span data-ttu-id="b225f-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b225f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b225f-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b225f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b225f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b225f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b225f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b225f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b225f-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="b225f-116">See also</span></span>
