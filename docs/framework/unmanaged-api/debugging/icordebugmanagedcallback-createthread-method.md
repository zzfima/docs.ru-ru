---
title: Метод ICorDebugManagedCallback::CreateThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48e92c73347957d8acc5c209f6f5473e9e18524
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223255"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="76154-102">Метод ICorDebugManagedCallback::CreateThread</span><span class="sxs-lookup"><span data-stu-id="76154-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="76154-103">Уведомляет отладчик о том, что поток начал выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="76154-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76154-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76154-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76154-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76154-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="76154-106">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит поток.</span><span class="sxs-lookup"><span data-stu-id="76154-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="76154-107">[in] Указатель на объект ICorDebugThread, представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="76154-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76154-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="76154-108">Remarks</span></span>  
 <span data-ttu-id="76154-109">Поток будет расположен в первой инструкции для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="76154-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76154-110">Требования</span><span class="sxs-lookup"><span data-stu-id="76154-110">Requirements</span></span>  
 <span data-ttu-id="76154-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76154-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76154-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76154-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76154-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76154-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="76154-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="76154-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="76154-115">См. также</span><span class="sxs-lookup"><span data-stu-id="76154-115">See also</span></span>

- [<span data-ttu-id="76154-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="76154-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
