---
title: Метод ICorDebugManagedCallback::LoadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfca06c656f3274f4c5ddb06373a0296dc5e6905
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164545"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="0c4de-102">Метод ICorDebugManagedCallback::LoadModule</span><span class="sxs-lookup"><span data-stu-id="0c4de-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="0c4de-103">Уведомляет отладчик, что общий модуль среды выполнения (CLR) язык был успешно загружен.</span><span class="sxs-lookup"><span data-stu-id="0c4de-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c4de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c4de-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c4de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c4de-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0c4de-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в который загружен модуль.</span><span class="sxs-lookup"><span data-stu-id="0c4de-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="0c4de-107">[in] Указатель на объект ICorDebugModule, который представляет модуль среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0c4de-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c4de-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c4de-108">Remarks</span></span>  
 <span data-ttu-id="0c4de-109">`LoadModule` Обратного вызова предоставляет подходящий момент для просмотра метаданных для модуля, задать флаги компилятора just-in-time (JIT), или включить или отключить обратные вызовы для модуля загрузки.</span><span class="sxs-lookup"><span data-stu-id="0c4de-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c4de-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0c4de-110">Requirements</span></span>  
 <span data-ttu-id="0c4de-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c4de-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c4de-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c4de-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c4de-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c4de-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0c4de-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0c4de-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c4de-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0c4de-115">See also</span></span>

- [<span data-ttu-id="0c4de-116">Метод UnloadModule</span><span class="sxs-lookup"><span data-stu-id="0c4de-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="0c4de-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0c4de-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
