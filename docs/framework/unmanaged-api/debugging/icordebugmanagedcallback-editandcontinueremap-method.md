---
title: Метод ICorDebugManagedCallback::EditAndContinueRemap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1bdb14e8c3a61a2b94cef778660eeb5c85c34df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988251"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="2e720-102">Метод ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="2e720-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="2e720-103">Этот метод использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="2e720-103">This method has been deprecated.</span></span> <span data-ttu-id="2e720-104">Он уведомляет отладчик, что события повторного сопоставления, отправленные в интегрированной среде разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="2e720-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e720-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e720-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="2e720-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e720-106">Remarks</span></span>  
 <span data-ttu-id="2e720-107">`EditAndContinueRemap` Метод вызывается в том случае, когда предпринята попытка выполнения кода в старой версии обновленной функции.</span><span class="sxs-lookup"><span data-stu-id="2e720-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="2e720-108">Среда CLR вызывает выполнения `EditAndContinueRemap` метод для отправки события повторного сопоставления в интегрированную среду разработки.</span><span class="sxs-lookup"><span data-stu-id="2e720-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e720-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2e720-109">Requirements</span></span>  
 <span data-ttu-id="2e720-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e720-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e720-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e720-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e720-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e720-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e720-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e720-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e720-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2e720-114">See also</span></span>

- [<span data-ttu-id="2e720-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="2e720-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
