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
ms.openlocfilehash: 51ee8b3631bffe9fd7fef4351e0aa67d1cbbe2c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125397"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>Метод ICorDebugController::HasQueuedCallbacks
Возвращает значение, указывающее, находятся ли в очереди управляемые обратные вызовы для указанного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pThread`  
 окне Указатель на объект "ICorDebugThread", представляющий поток.  
  
 `pbQueued`  
 заполняет Указатель на значение, которое `true`, если в настоящий момент в очереди для указанного потока находятся управляемые обратные вызовы. в противном случае `false`.  
  
 Если для параметра `pThread` указано значение null, `HasQueuedCallbacks` будет возвращать `true`, если в настоящий момент в очереди есть управляемые обратные вызовы для любого потока.  
  
## <a name="remarks"></a>Заметки  
 Обратные вызовы будут отправлены по одному, каждый раз, когда вызывается [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) . Отладчик может проверить этот флаг, если он хочет сообщить о нескольких событиях отладки, происходящих одновременно.  
  
 Когда события отладки помещаются в очередь, они уже были выполнены, поэтому отладчик должен очистить всю очередь, чтобы убедиться в состоянии отлаживаемой программы. (Вызовите `ICorDebugController::Continue` для очистки очереди.) Например, если очередь содержит два события отладки в потоке *x*, а отладчик приостанавливает поток *x* после первого события отладки и затем вызывает `ICorDebugController::Continue`, второе событие отладки для потока *X* будет отправлено, хотя поток был приостановлен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
