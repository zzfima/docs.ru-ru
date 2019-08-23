---
title: Метод ICorDebugController::Stop
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 363d8f7d8cf960fb23210225c4545f73d597d663
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912842"
---
# <a name="icordebugcontrollerstop-method"></a>Метод ICorDebugController::Stop
Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwTimeoutIgnored`  
 Не используется.  
  
## <a name="remarks"></a>Примечания  
 `Stop`выполняет совместную работу всех потоков, выполняющих управляемый код в процессе. Во время сеанса отладки, доступного только для управляемого кода, неуправляемые потоки могут продолжать выполняться (но будут заблокированы при попытке вызвать управляемый код). Во время сеанса отладки взаимодействия неуправляемые потоки также будут остановлены. `dwTimeoutIgnored` Значение в настоящее время игнорируется и обрабатывается как бесконечное (-1). Если совместная остановка завершается сбоем из-за взаимоблокировки, все потоки приостанавливаются и возвращается E_TIMEOUT.  
  
> [!NOTE]
> `Stop`— единственный синхронный метод в API отладки. Если `Stop` метод возвращает значение S_OK, процесс останавливается. Обратный вызов не предоставляется для уведомления прослушивателей об ошибке. Отладчик должен вызвать [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , чтобы разрешить возобновление процесса.  
  
 Отладчик поддерживает счетчик "останавливается". Когда счетчик переходит в нулевое значение, контроллер возобновляется. Каждый вызов `Stop` или каждый отправленный обратный вызов увеличивает счетчик. Каждый вызов `ICorDebugController::Continue` уменьшает значение счетчика.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
