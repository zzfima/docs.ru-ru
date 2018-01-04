---
title: "Метод ICorDebugManagedCallback::LogMessage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LogMessage
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62204e8fb2e1fabae4183bbcf7b4d42b832d2b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="46ab9-102">Метод ICorDebugManagedCallback::LogMessage</span><span class="sxs-lookup"><span data-stu-id="46ab9-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="46ab9-103">Уведомляет отладчик о том, что обычная практика среда CLR управляемого языка вызвал метод в <xref:System.Diagnostics.EventLog> класс события в журнал.</span><span class="sxs-lookup"><span data-stu-id="46ab9-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46ab9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46ab9-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46ab9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46ab9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="46ab9-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий управляемый поток, зарегистрировавшее событие.</span><span class="sxs-lookup"><span data-stu-id="46ab9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="46ab9-107">[in] Указатель на объект ICorDebugThread, который представляет управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="46ab9-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="46ab9-108">[in] Значение [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) значение перечисления, указывающее уровень важности описательного сообщения, зафиксированной в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="46ab9-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="46ab9-109">[in] Указатель на имя переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="46ab9-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="46ab9-110">[in] Указатель на сообщения, которые были записаны в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="46ab9-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46ab9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="46ab9-111">Requirements</span></span>  
 <span data-ttu-id="46ab9-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46ab9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46ab9-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46ab9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46ab9-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46ab9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46ab9-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46ab9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ab9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="46ab9-116">See Also</span></span>  
 [<span data-ttu-id="46ab9-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="46ab9-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
