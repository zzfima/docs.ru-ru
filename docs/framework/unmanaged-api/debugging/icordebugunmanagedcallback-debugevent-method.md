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
ms.openlocfilehash: 2d865f837d38894e8449af671e2d12e7676dd040
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129137"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>Метод ICorDebugUnmanagedCallback::DebugEvent
Уведомляет отладчик о срабатывании собственного события.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pDebugEvent`  
 окне Указатель на собственное событие.  
  
 `fOutOfBand`  
 [in] `true`, если взаимодействие с состоянием управляемого процесса невозможно после возникновения неуправляемого события, пока отладчик не вызовет [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); в противном случае `false`.  
  
## <a name="remarks"></a>Заметки  
 Если отлаживаемый поток является потоком Win32, не используйте члены интерфейса отладки Win32. Можно вызвать `ICorDebugController::Continue` только в потоке Win32 и продолжить событие за пределами внешнего управления.  
  
 Обратный вызов `DebugEvent` не соответствует стандартным правилам для обратных вызовов. При вызове `DebugEvent`процесс будет остановлен в состоянии "необработанный", "ОС-Отладка". Процесс не будет синхронизирован. Он автоматически вводит синхронизированное состояние при необходимости для удовлетворения запросов сведений об управляемом коде, что может привести к другим вложенным обратным вызовам `DebugEvent`.  
  
 Перед продолжением процесса вызовите [ICorDebugProcess:: ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) в процессе, чтобы проигнорировать событие исключения. Вызов этого метода отправляет DBG_CONTINUE вместо DBG_EXCEPTION_NOT_HANDLED в запросе continue и автоматически очищает точки останова по промежуточному каналу и одношаговые исключения. События по внешнему каналу могут быть получены в любое время, даже если отладка приложения будет остановлена и когда уже существует необработанное событие в полосе.  
  
 В .NET Framework версии 2,0 отладчик должен немедленно продолжить работу после события нестандартной точки останова. Для добавления и удаления точек останова отладчик должен использовать методы [ICorDebugProcess2:: сетунманажедбреакпоинт](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) и [ICorDebugProcess2:: клеарунманажедбреакпоинт](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) . Эти методы будут автоматически пропускать любые точки останова по внешнему каналу. Таким образом, только точки останова по внешнему каналу, которые были отправлены, должны быть необработанными точками останова, которые уже находятся в потоке инструкций, например в вызове функции Win32 `DebugBreak`. Не пытайтесь использовать `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)или любой другой член [API отладки](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
