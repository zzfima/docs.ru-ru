---
title: Метод ICorDebugController::HasQueuedCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eba265b727d00690ab77c6ae831e954d59df7c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411614"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>Метод ICorDebugController::HasQueuedCallbacks
Возвращает значение, указывающее ли любого управляемого обратных вызовов в настоящее время в очереди для заданного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pThread`  
 [in] Указатель на объект «ICorDebugThread», представляющий поток.  
  
 `pbQueued`  
 [out] Указатель на значение, являющееся `true` Если любой управляемый обратных вызовов в настоящий момент в очереди для указанного потока, в противном случае — `false`.  
  
 Если указано значение null для `pThread` параметр `HasQueuedCallbacks` вернет `true` Если в настоящий момент в очереди управляемого обратные вызовы для любого потока.  
  
## <a name="remarks"></a>Примечания  
 Обратные вызовы будет отправлено по одному, каждый раз [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) вызывается. Отладчик может установить этот флаг, если ему нужно сообщить нескольких событиях отладки, которые произошли одновременно.  
  
 Постановке в очередь событий отладки, они уже произошли, поэтому отладчик должен обработать всю очередь, чтобы штата отлаживаемого кода. (Вызов `ICorDebugController::Continue` истощения очереди.) Например, если очередь содержит два события отладки потока *X*, и отладчик приостанавливает выполнение потока *X* после первого события отладки, а затем вызывает `ICorDebugController::Continue`, второе событие отладки для поток *X* будет отправлено, несмотря на то, что этот поток был приостановлен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
