---
title: "Метод ICorDebugController::Continue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Continue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 93fc138b8610d252be5c3ca3821bb1d41c5ac6ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollercontinue-method"></a>Метод ICorDebugController::Continue
Возобновление выполнения управляемых потоков после вызова [метод Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fIsOutOfBand`  
 [in] Значение `true` в событие по каналу; в противном случае — значение `false`.  
  
## <a name="remarks"></a>Примечания  
 `Continue`Продолжение процесса после вызова `ICorDebugController::Stop` метод.  
  
 При выполнении отладки в смешанном режиме, не следует вызывать `Continue` на Win32 событий потока, если необходимо продолжить из события по каналу.  
  
 *В противном случае* управляемое событие или обычное неуправляемое событие, во время которого отладчик поддерживает взаимодействие с управляемым состоянием процесса. В этом случае отладчик получает [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) обратного вызова с его `fOutOfBand` равным `false`.  
  
 *Событий по каналу* неуправляемые событие во время которого взаимодействие с управляемым состоянием процесса невозможна, пока процесс остановлен из-за событие. В этом случае отладчик получает `ICorDebugUnmanagedCallback::DebugEvent` обратного вызова с его `fOutOfBand` равным `true`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 
