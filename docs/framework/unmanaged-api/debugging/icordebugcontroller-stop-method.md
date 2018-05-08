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
ms.openlocfilehash: 2cd0fc9f86515d63533275002301eb47f11feebb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollerstop-method"></a>Метод ICorDebugController::Stop
Выполняет совместную остановку всех потоков, выполняющих управляемый код в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwTimeoutIgnored`  
 Не используется.  
  
## <a name="remarks"></a>Примечания  
 `Stop` выполняет согласованную остановку всех потоков, выполняющих управляемый код в процессе. Во время сеанса отладки только управляемого, неуправляемые потоки может продолжить свое выполнение (но будет блокироваться при попытке вызова управляемого кода). Во время сеанса отладки взаимодействия также можно остановить неуправляемые потоки. `dwTimeoutIgnored` В настоящее время значение игнорируется и обрабатывается как INFINITE (-1). Если согласованная остановка завершилась сбоем из-за взаимоблокировки, все потоки приостанавливаются и возвращается значение E_TIMEOUT.  
  
> [!NOTE]
>  `Stop` является единственным методом синхронизации в API отладки. Если `Stop` возвращает значение S_OK, процесс останавливается. Обратный вызов не предоставляется для уведомления прослушивателей об остановке. Отладчик должен вызвать [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) позволяет возобновить процесс.  
  
 Отладчик поддерживает счетчик stop. Когда значение счетчика становится равным нулю, возобновляется контроллера. Каждый вызов `Stop` или каждого отправленного обратного вызова увеличивает на единицу счетчик. Каждый вызов `ICorDebugController::Continue` уменьшает значение счетчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
