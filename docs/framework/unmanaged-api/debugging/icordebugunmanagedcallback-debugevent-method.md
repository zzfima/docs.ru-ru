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
ms.openlocfilehash: 51ccc7b1b50613f0d2b44a9e101314128782c412
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423134"
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
  
#### <a name="parameters"></a>Параметры  
 `pDebugEvent`  
 [in] Указатель на собственный событий.  
  
 `fOutOfBand`  
 [in] `true`, если невозможно взаимодействие с состоянием управляемого процесса после возникновения события неуправляемым, пока отладчик вызывает [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Если отлаживаемый поток является потоком Win32, не используйте никакие элементы Win32 интерфейса отладки. Можно вызвать `ICorDebugController::Continue` только потоком Win32 и только в том случае, если продолжение после события по каналу.  
  
 `DebugEvent` Обратного вызова не действуют стандартные правила для обратных вызовов. При вызове `DebugEvent`, процесс будет находиться в необработанный, состоянии остановки отладки операционной Системой. Процесс не будут синхронизированы. Автоматически перейдет в состояние синхронизации при необходимости выполнить запрос для получения сведений об управляемом коде, что может стать причиной других вложенных `DebugEvent` обратные вызовы.  
  
 Вызовите [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) в процессе, чтобы пропустить событие исключения перед продолжением процесса. Вызов этого метода отправляет продолжения вместо DBG_EXCEPTION_NOT_HANDLED продолжить запроса, а также автоматически очищает по каналу точки останова и пошагово исключения. События по каналу могут поступать в любое время, даже в том случае, если останавливается отлаживаемого приложения и необработанные события по каналу уже существует.  
  
 В платформе .NET Framework версии 2.0 отладчик должен немедленно продолжить прошлое событие точки останова по каналу. Отладчик должен использовать [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) и [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) методы для добавления и удаления точек останова. Эти методы будут автоматически пропускать все точки останова по каналу. Таким образом, только для аппаратного точки останова, которые отправить должно быть точками останова, которые уже находятся в поток инструкций, например вызов Win32 `DebugBreak` функции. Не пытайтесь использовать `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), или любого другого элемента [API отладки](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
