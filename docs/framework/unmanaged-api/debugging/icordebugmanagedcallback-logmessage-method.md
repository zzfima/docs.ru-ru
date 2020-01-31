---
title: Метод ICorDebugManagedCallback::LogMessage
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 4306c4ae44b0ae1ade2bf374981492fa1a4df76f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788369"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="5f74d-102">Метод ICorDebugManagedCallback::LogMessage</span><span class="sxs-lookup"><span data-stu-id="5f74d-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="5f74d-103">Уведомляет отладчик о том, что управляемый поток среды CLR вызвал метод в классе <xref:System.Diagnostics.EventLog> для записи события в журнал.</span><span class="sxs-lookup"><span data-stu-id="5f74d-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f74d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f74d-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f74d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f74d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5f74d-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток, который зарегистрировал событие.</span><span class="sxs-lookup"><span data-stu-id="5f74d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5f74d-107">окне Указатель на объект ICorDebugThread, представляющий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="5f74d-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="5f74d-108">окне Значение перечисления [логгинглевеленум](logginglevelenum-enumeration.md) , указывающее степень серьезности описательного сообщения, записанного в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="5f74d-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="5f74d-109">окне Указатель на имя переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f74d-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="5f74d-110">окне Указатель на сообщение, записанное в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="5f74d-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f74d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5f74d-111">Requirements</span></span>  
 <span data-ttu-id="5f74d-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f74d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f74d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f74d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f74d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f74d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f74d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f74d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f74d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f74d-116">See also</span></span>

- [<span data-ttu-id="5f74d-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5f74d-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
