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
ms.openlocfilehash: 425c606b1f340bbd49cfe3497d394d5ad0dd37a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763806"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>Метод ICorDebugManagedCallback2::MDANotification
Предоставляет уведомление, что выполнение кода обнаружил помощник по отладке управляемого (кода MDA) в отлаживаемом приложении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pController`  
 [in] Указатель на интерфейс ICorDebugController, предоставляющей процесса или домена приложения, в котором произошло MDA.  
  
 Отладчик не следует вносить никаких предположений о том, является ли контроллер процесс или домен приложения, несмотря на то, что он всегда может запросить интерфейс принимать решения.  
  
 `pThread`  
 [in] Указатель на интерфейс ICorDebugThread, который предоставляет управляемый поток, в котором произошло событие отладки.  
  
 Если произошла по отладке управляемого кода в неуправляемый поток, значение `pThread` будет иметь значение null.  
  
 Из самого объекта по отладке управляемого кода необходимо получить идентификатор потока операционной системы (ОС).  
  
 `pMDA`  
 [in] Указатель на [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) интерфейс, предоставляющий сведения по отладке управляемого кода.  
  
## <a name="remarks"></a>Примечания  
 MDA — это эвристическое предупреждение и не требует никаких действий явные отладчика, за исключением вызова [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) возобновить выполнение отлаживаемого приложения.  
  
 Среда CLR (CLR) можно определить MDA, и какие данные оказываются в любой данный MDA, в любой момент. Таким образом отладчики не должны строить любые функции, требующие определенных шаблонов по отладке управляемого кода.  
  
 Помощники отладки управляемого кода в очередь и вызывать сразу же после обнаружения. Это может произойти, если среда выполнения должна ждать, пока он достигает безопасной точки для вызова MDA, вместо вызова MDA при ее обнаружении. Это также означает, что среда выполнения может возникнуть ряд Помощники отладки управляемого кода в один набор в очередь обратных вызовов (аналогично операции «присоединение» событий).  
  
 Отладчик должен освободить ссылку на `ICorDebugMDA` экземпляр сразу после возврата из `MDANotification` обратного вызова, чтобы разрешить CLR позволяет очистить память, занятая MDA. Освобождение экземпляра может повысить производительность, если нескольких MDA.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
