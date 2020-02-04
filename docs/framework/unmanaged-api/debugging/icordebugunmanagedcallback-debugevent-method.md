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
ms.openlocfilehash: cb52150a17c9ec8f4bbc25c13b85bce56b221eeb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791194"
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
 [in] `true`, если взаимодействие с состоянием управляемого процесса невозможно после возникновения неуправляемого события, пока отладчик не вызовет [ICorDebugController:: Continue](icordebugcontroller-continue-method.md); в противном случае `false`.  
  
## <a name="remarks"></a>Заметки  
 Если отлаживаемый поток является потоком Win32, не используйте члены интерфейса отладки Win32. Можно вызвать `ICorDebugController::Continue` только в потоке Win32 и продолжить событие за пределами внешнего управления.  
  
 Обратный вызов `DebugEvent` не соответствует стандартным правилам для обратных вызовов. При вызове `DebugEvent`процесс будет остановлен в состоянии "необработанный", "ОС-Отладка". Процесс не будет синхронизирован. Он автоматически вводит синхронизированное состояние при необходимости для удовлетворения запросов сведений об управляемом коде, что может привести к другим вложенным обратным вызовам `DebugEvent`.  
  
 Перед продолжением процесса вызовите [ICorDebugProcess:: ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) в процессе, чтобы проигнорировать событие исключения. Вызов этого метода отправляет DBG_CONTINUE вместо DBG_EXCEPTION_NOT_HANDLED в запросе continue и автоматически очищает невыполненные точки останова и одношаговые исключения. События по внешнему каналу могут быть получены в любое время, даже если отладка приложения будет остановлена и когда уже существует необработанное событие в полосе.  
  
 В .NET Framework версии 2,0 отладчик должен немедленно продолжить работу после события нестандартной точки останова. Для добавления и удаления точек останова отладчик должен использовать методы [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md) и [ICorDebugProcess2:: клеарунманажедбреакпоинт](icordebugprocess2-clearunmanagedbreakpoint-method.md) . Эти методы будут автоматически пропускать любые точки останова по внешнему каналу. Таким образом, только точки останова по внешнему каналу, которые были отправлены, должны быть необработанными точками останова, которые уже находятся в потоке инструкций, например в вызове функции Win32 `DebugBreak`. Не пытайтесь использовать `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](icordebugprocess-setthreadcontext-method.md)или любой другой член [API отладки](index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)
