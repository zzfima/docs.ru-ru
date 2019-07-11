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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14b10b94f66a6b5434befeac1cd9562cb8a0f27f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761557"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="5b45f-102">Метод ICorDebugManagedCallback::LogMessage</span><span class="sxs-lookup"><span data-stu-id="5b45f-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="5b45f-103">Уведомляет отладчик о том, что нитью среды выполнения (CLR) управляемый язык вызвал метод <xref:System.Diagnostics.EventLog> класс события в журнал.</span><span class="sxs-lookup"><span data-stu-id="5b45f-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b45f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b45f-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b45f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b45f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5b45f-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий управляемый поток, который зафиксировал событие.</span><span class="sxs-lookup"><span data-stu-id="5b45f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5b45f-107">[in] Указатель на объект ICorDebugThread, который представляет управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="5b45f-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="5b45f-108">[in] Значение [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) перечисление, указывающее степень серьезности описательное сообщение, которые были записаны в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="5b45f-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="5b45f-109">[in] Указатель на имя переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="5b45f-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="5b45f-110">[in] Указатель на сообщения, которые были записаны в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="5b45f-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b45f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5b45f-111">Requirements</span></span>  
 <span data-ttu-id="5b45f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b45f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b45f-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b45f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b45f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b45f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b45f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b45f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b45f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5b45f-116">See also</span></span>

- [<span data-ttu-id="5b45f-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5b45f-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
