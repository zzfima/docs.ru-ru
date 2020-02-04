---
title: Метод ICorDebugManagedCallback2::MDANotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: bf9ea40cc81be37499e6729006e7177a8000c000
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793301"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>Метод ICorDebugManagedCallback2::MDANotification
Предоставляет уведомление о том, что при выполнении кода в отлаживаемом приложении обнаружен управляемый помощник по отладке (MDA).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pController`  
 окне Указатель на интерфейс ICorDebugController, предоставляющий процесс или домен приложения, в котором выполнялся MDA.  
  
 Отладчик не должен делать никаких предположений относительно того, является ли контроллер процессом или доменом приложения, хотя он всегда может запрашивать интерфейс для выполнения определения.  
  
 `pThread`  
 окне Указатель на интерфейс ICorDebugThread, предоставляющий управляемый поток, в котором произошло событие отладки.  
  
 Если MDA произошло в неуправляемом потоке, значение `pThread` будет равно null.  
  
 Необходимо получить идентификатор потока операционной системы (ОС) из самого объекта MDA.  
  
 `pMDA`  
 окне Указатель на интерфейс [ICorDebugMDA](icordebugmda-interface.md) , предоставляющий сведения об MDA.  
  
## <a name="remarks"></a>Заметки  
 MDA является эвристическим предупреждением и не требует явных действий отладчика, за исключением вызова [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) для возобновления выполнения отлаживаемого приложения.  
  
 Общеязыковая среда выполнения (CLR) может определять, какие MDA срабатывают и какие данные находятся в любом заданном MDA в любой момент времени. Таким образом, отладчики не должны создавать функции, требующие специальных шаблонов MDA.  
  
 Помощники MDA могут быть поставлены в очередь и срабатывать вскоре после обнаружения помощника по отладке управляемого кода. Это может произойти, если среде выполнения необходимо подождать, пока она достигнет надежной точки для запуска MDA, вместо того, чтобы использовать MDA при обнаружении. Это также означает, что среда выполнения может запустить несколько MDA в одном наборе обратных вызовов в очереди (аналогично операции "присоединение").  
  
 Отладчик должен освободить ссылку на экземпляр `ICorDebugMDA` сразу после возврата из обратного вызова `MDANotification`, чтобы разрешить среде CLR перезапустить память, занятую MDA. Освобождение экземпляра может повысить производительность при срабатывании многих MDA.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
