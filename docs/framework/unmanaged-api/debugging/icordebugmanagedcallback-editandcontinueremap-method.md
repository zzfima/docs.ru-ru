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
ms.openlocfilehash: 9e8aa71a79bee45d5a8e1f3448c781e6ba1ec605
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414142"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="c44f3-102">Метод ICorDebugManagedCallback::EditAndContinueRemap</span><span class="sxs-lookup"><span data-stu-id="c44f3-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="c44f3-103">Этот метод использовать не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="c44f3-103">This method has been deprecated.</span></span> <span data-ttu-id="c44f3-104">Он уведомляет отладчик, что события повторного сопоставления был отправлен интегрированной среды разработки (IDE).</span><span class="sxs-lookup"><span data-stu-id="c44f3-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44f3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c44f3-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="c44f3-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c44f3-106">Remarks</span></span>  
 <span data-ttu-id="c44f3-107">`EditAndContinueRemap` Метод вызывается, когда предпринята попытка выполнения кода в старой версии обновленной функции.</span><span class="sxs-lookup"><span data-stu-id="c44f3-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="c44f3-108">Среда CLR вызывает выполнения `EditAndContinueRemap` метод для отправки события повторного сопоставления в интегрированную среду разработки.</span><span class="sxs-lookup"><span data-stu-id="c44f3-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c44f3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c44f3-109">Requirements</span></span>  
 <span data-ttu-id="c44f3-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c44f3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c44f3-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c44f3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c44f3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c44f3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c44f3-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c44f3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44f3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c44f3-114">See Also</span></span>  
 [<span data-ttu-id="c44f3-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c44f3-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
