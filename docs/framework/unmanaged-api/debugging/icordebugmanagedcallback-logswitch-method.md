---
title: "Метод ICorDebugManagedCallback::LogSwitch"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LogSwitch
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9480b3123abceb6a108e2e00c7304829188cd162
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="ca66e-102">Метод ICorDebugManagedCallback::LogSwitch</span><span class="sxs-lookup"><span data-stu-id="ca66e-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="ca66e-103">Уведомляет отладчик о том, что обычная практика среда CLR управляемого языка вызвал метод в <xref:System.Diagnostics.Switch> класса для создания, изменения или удаления переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca66e-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca66e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca66e-104">Syntax</span></span>  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca66e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca66e-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="ca66e-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий управляемый поток, который создан, изменен или удален переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca66e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ca66e-107">[in] Указатель на объект ICorDebugThread, который представляет управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="ca66e-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="ca66e-108">[in] Значение, указывающее уровень важности описательного сообщения, зафиксированной в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="ca66e-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="ca66e-109">[in] Значение [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) перечисления, которое указывает, что операция выполняется на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca66e-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="ca66e-110">[in] Указатель на имя коммутатора отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca66e-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="ca66e-111">[in] Указатель на имя родительского элемента переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca66e-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca66e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ca66e-112">Requirements</span></span>  
 <span data-ttu-id="ca66e-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca66e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca66e-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca66e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca66e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca66e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca66e-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca66e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca66e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ca66e-117">See Also</span></span>  
 [<span data-ttu-id="ca66e-118">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ca66e-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
