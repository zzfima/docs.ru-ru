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
ms.openlocfilehash: af2dab65629093401219f1016538b912bee4d067
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130824"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="9d2c5-102">Метод ICorDebugManagedCallback::Exception</span><span class="sxs-lookup"><span data-stu-id="9d2c5-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="9d2c5-103">Уведомляет отладчик о появлении исключения из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9d2c5-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d2c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d2c5-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d2c5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d2c5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9d2c5-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="9d2c5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="9d2c5-107">окне Указатель на объект ICorDebugThread, представляющий поток, в котором было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="9d2c5-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="9d2c5-108">окне Если это значение равно `false`, исключение еще не было обработано приложением; в противном случае исключение не обработано, и процесс завершится.</span><span class="sxs-lookup"><span data-stu-id="9d2c5-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d2c5-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="9d2c5-109">Remarks</span></span>  
 <span data-ttu-id="9d2c5-110">Конкретное исключение можно получить из объекта потока.</span><span class="sxs-lookup"><span data-stu-id="9d2c5-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d2c5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9d2c5-111">Requirements</span></span>  
 <span data-ttu-id="9d2c5-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d2c5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d2c5-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d2c5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d2c5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d2c5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d2c5-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d2c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2c5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9d2c5-116">See also</span></span>

- [<span data-ttu-id="9d2c5-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9d2c5-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
