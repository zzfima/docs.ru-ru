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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64b09c173e2f66d4c650083cc12f8a0ac2c92007
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>Метод ICorDebugManagedCallback2::MDANotification
Предоставляет уведомление о том, что выполнение кода обнаружил помощник по отладке управляемого (кода MDA) в отлаживаемом приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pController`  
 [in] Указатель на интерфейс ICorDebugController, предоставляющую процесс или домен приложения, в котором произошло MDA.  
  
 Отладчик не следует делать никаких предположений о типе контроллера: процесс или домен приложения, несмотря на то, что он всегда может запросить выполнение такого определения интерфейса.  
  
 `pThread`  
 [in] Указатель на интерфейс ICorDebugThread, который представляет управляемый поток, в котором произошло событие отладки.  
  
 Если MDA встречается на неуправляемый поток, значение `pThread` будет иметь значение null.  
  
 Из самого объекта MDA, необходимо получить идентификатор потока операционной системы (ОС).  
  
 `pMDA`  
 [in] Указатель на [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) интерфейс, который предоставляет сведения об MDA.  
  
## <a name="remarks"></a>Примечания  
 MDA — это эвристическое предупреждение и не требуют никакого отладчика явного действия, за исключением вызова [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) для возобновления выполнения отлаживаемого приложения.  
  
 Общеязыковая среда выполнения (CLR) можно определить MDA, и какие данные оказываются в любой данный MDA в любой момент. Таким образом отладчики не должны использовать все функции, требующие определенных шаблонов управляемого кода.  
  
 Помощники отладки управляемого кода может быть в очередь и вызывать сразу же после обнаружения. Это может произойти, если среда выполнения должна ожидать, пока не достигнет безопасной точки для вызова управляемого кода, вместо вызова MDA при его обнаружении. Это также означает, что среда выполнения может вызвать несколько помощников в один набор в очередь обратных вызовов (аналогично операции события «присоединить»).  
  
 Отладчик должен освободить ссылку на `ICorDebugMDA` экземпляр сразу после возврата из `MDANotification` обратного вызова, чтобы разрешить CLR повторно использовать память, занятая MDA. Освобождение экземпляра может повысить производительность, если нескольких MDA.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
