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
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130697"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="ce90d-102">Метод ICorDebugManagedCallback::LogSwitch</span><span class="sxs-lookup"><span data-stu-id="ce90d-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="ce90d-103">Уведомляет отладчик о том, что управляемый поток среды CLR вызвал метод в классе <xref:System.Diagnostics.Switch> для создания, изменения или удаления переключателя отладки или трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce90d-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce90d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce90d-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce90d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce90d-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="ce90d-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток, который создал, изменил или удалил параметр отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce90d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ce90d-107">окне Указатель на объект ICorDebugThread, представляющий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="ce90d-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="ce90d-108">окне Значение, указывающее степень серьезности описательного сообщения, записанного в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="ce90d-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="ce90d-109">окне Значение перечисления [логсвитчкаллреасон](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) , указывающее операцию, выполняемую с переключателем "Отладка/трассировка".</span><span class="sxs-lookup"><span data-stu-id="ce90d-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="ce90d-110">окне Указатель на имя переключателя отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="ce90d-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="ce90d-111">окне Указатель на имя родителя переключателя "Отладка/трассировка".</span><span class="sxs-lookup"><span data-stu-id="ce90d-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce90d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ce90d-112">Requirements</span></span>  
 <span data-ttu-id="ce90d-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce90d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce90d-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce90d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce90d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce90d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce90d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce90d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce90d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ce90d-117">See also</span></span>

- [<span data-ttu-id="ce90d-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ce90d-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
