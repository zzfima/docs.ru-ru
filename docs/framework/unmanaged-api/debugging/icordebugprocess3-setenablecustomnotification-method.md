---
title: "Метод ICorDebugProcess3::SetEnableCustomNotification"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess3.SetEnableCustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ccd1f4b6be56202d5efea1d2e38dce554835218
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>Метод ICorDebugProcess3::SetEnableCustomNotification
Включает и отключает пользовательскими уведомлениями отладчика заданного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pClass`  
 [in] Тип, определяющий пользовательскими уведомлениями отладчика.  
  
 `fEnable`  
 [in] `true` Включение пользовательскими уведомлениями отладчика; `false` отключения уведомлений. Значение по умолчанию — `false`.  
  
## <a name="remarks"></a>Примечания  
 Когда `fEnable` задано значение `true`, вызовы <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> триггер метод [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) обратного вызова. Уведомления отключены по умолчанию. Таким образом отладчик необходимо указать все типы уведомлений, он знает об и требуется обрабатывать. Поскольку [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) действия класса доменом приложения, отладчик должен вызвать `SetEnableCustomNotification` для каждого домена приложений в процессе, если требуется получать уведомления из всего процесса.  
  
 Начиная с [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], единственным поддерживаемым уведомлением является уведомление зависимости между потоками.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
