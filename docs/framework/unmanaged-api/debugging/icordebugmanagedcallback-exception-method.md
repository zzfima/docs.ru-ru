---
title: Метод ICorDebugManagedCallback::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e985d82fcce404e15344f2277d27a6aab45f9efc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472512"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="7d546-102">Метод ICorDebugManagedCallback::Exception</span><span class="sxs-lookup"><span data-stu-id="7d546-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="7d546-103">Уведомляет отладчик о том, что исключение выдавалось из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7d546-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d546-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d546-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d546-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d546-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7d546-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="7d546-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7d546-107">[in] Указатель на объект ICorDebugThread, представляющий поток, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="7d546-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="7d546-108">[in] Если это значение равно `false`, исключение еще не был обработан элементом приложения; в противном случае, исключение остается необработанным и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="7d546-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d546-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d546-109">Remarks</span></span>  
 <span data-ttu-id="7d546-110">Конкретное исключение можно получить из объекта потока.</span><span class="sxs-lookup"><span data-stu-id="7d546-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d546-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7d546-111">Requirements</span></span>  
 <span data-ttu-id="7d546-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d546-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d546-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d546-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d546-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d546-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d546-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d546-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d546-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7d546-116">See also</span></span>
- [<span data-ttu-id="7d546-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7d546-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
