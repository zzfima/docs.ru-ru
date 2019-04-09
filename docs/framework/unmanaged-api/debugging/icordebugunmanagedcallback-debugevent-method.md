---
title: Метод ICorDebugUnmanagedCallback::DebugEvent
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ec45004f5dd87983187690a0a4feefb35b05e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183616"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>Метод ICorDebugUnmanagedCallback::DebugEvent
Уведомляет отладчик о том, что произошло событие машинного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pDebugEvent`  
 [in] Указатель на собственный события.  
  
 `fOutOfBand`  
 [in] `true`, если взаимодействие с состоянием управляемого процесса невозможна после возникновения события неуправляемые, пока отладчик не вызовет [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Если отлаживаемый поток является потоком Win32, не используйте ни с одним элементом Win32 интерфейса отладки. Вы можете вызвать `ICorDebugController::Continue` только в потоке Win32 и только в том случае, если продолжение за-внешнее событие.  
  
 `DebugEvent` Обратного вызова не соответствуют стандартным правилам для обратных вызовов. При вызове `DebugEvent`, процесс будет находиться в необработанный, состоянии остановки отладки операционной системы. Процесс не будут синхронизированы. Он автоматически войдет в синхронизированном состоянии, когда необходимо выполнить запрос сведений об управляемом коде, что может вызвать другие вложенные `DebugEvent` обратные вызовы.  
  
 Вызовите [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) на процесс, чтобы пропустить событие исключения, прежде чем продолжить процесс. Вызов этого метода отправляет продолжения вместо DBG_EXCEPTION_NOT_HANDLED на запроса на продолжение, а также автоматически очищает-резервному точки останова и одношаговые исключения. Out of band события могут поступать в любое время, даже в том случае, если отлаживаемого приложения останавливается, и необработанные события внутренней уже существует.  
  
 В .NET Framework версии 2.0 отладчик должен немедленно продолжить прошлое событие точки останова каналу. Отладчик должен использовать [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) и [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) методы для добавления и удаления точки останова. Эти методы будут автоматически пропускать все точки останова каналу. Таким образом, точки останова только-каналу, отправить должно быть точками останова, которые уже находятся в потоке инструкций, например вызов Win32 `DebugBreak` функции. Не пытайтесь использовать `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), или другой элемент [API отладки](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
