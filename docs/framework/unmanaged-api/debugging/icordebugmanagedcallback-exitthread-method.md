---
title: Метод ICorDebugManagedCallback::ExitThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37815d8aead1ec89826c13db6f012f2cd17bc792
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132448"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="b49c9-102">Метод ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="b49c9-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="b49c9-103">Уведомляет отладчик о завершении потока, время выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b49c9-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b49c9-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b49c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b49c9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b49c9-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="b49c9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="b49c9-107">[in] Указатель на объект ICorDebugThread, который представляет управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="b49c9-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b49c9-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b49c9-108">Remarks</span></span>  
 <span data-ttu-id="b49c9-109">Один раз `ExitThread` обратного вызова, поток больше не будет отображаться в перечислениях потоков.</span><span class="sxs-lookup"><span data-stu-id="b49c9-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b49c9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b49c9-110">Requirements</span></span>  
 <span data-ttu-id="b49c9-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b49c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b49c9-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b49c9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b49c9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b49c9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b49c9-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b49c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49c9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b49c9-115">See also</span></span>

- [<span data-ttu-id="b49c9-116">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b49c9-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
