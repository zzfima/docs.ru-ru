---
title: Метод ICorDebugManagedCallback::LogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a011485453999b9d764716356eebb2a5462f7bb9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078841"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="49e61-102">Метод ICorDebugManagedCallback::LogSwitch</span><span class="sxs-lookup"><span data-stu-id="49e61-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="49e61-103">Уведомляет отладчик о том, что нитью среды выполнения (CLR) управляемый язык вызвал метод <xref:System.Diagnostics.Switch> класса для создания, изменения или удаления коммутатора отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="49e61-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e61-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49e61-104">Syntax</span></span>  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49e61-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49e61-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="49e61-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий управляемый поток, который создан, изменен или удален переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="49e61-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="49e61-107">[in] Указатель на объект ICorDebugThread, который представляет управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="49e61-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="49e61-108">[in] Значение, указывающее уровень серьезности описательное сообщение, которые были записаны в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="49e61-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="49e61-109">[in] Значение [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) перечисление, указывающее, операции, выполняемые на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="49e61-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="49e61-110">[in] Указатель на имя переключателя отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="49e61-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="49e61-111">[in] Указатель на имя родительского элемента переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="49e61-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49e61-112">Требования</span><span class="sxs-lookup"><span data-stu-id="49e61-112">Requirements</span></span>  
 <span data-ttu-id="49e61-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49e61-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49e61-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49e61-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49e61-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49e61-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49e61-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49e61-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e61-117">См. также</span><span class="sxs-lookup"><span data-stu-id="49e61-117">See also</span></span>

- [<span data-ttu-id="49e61-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="49e61-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
