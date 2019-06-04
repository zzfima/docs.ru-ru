---
title: Метод ICorDebugProcess3::SetEnableCustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98084b179d27e97ecb3bb34525967d41f8ad1cb
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489610"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>Метод ICorDebugProcess3::SetEnableCustomNotification
Включает и отключает пользовательскими уведомлениями отладчика указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Параметры  
 `pClass`  
 [in] Тип, который задает пользовательскими уведомлениями отладчика.  
  
 `fEnable`  
 [in] `true` для включения пользовательскими уведомлениями отладчика; `false` отключение уведомлений. Значение по умолчанию — `false`.  
  
## <a name="remarks"></a>Примечания  
 Когда `fEnable` присваивается `true`, вызовы <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> триггера метод [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) обратного вызова. Уведомления отключены по умолчанию. Таким образом отладчик необходимо указать все типы уведомлений, он знает о и может обработать. Так как [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) действия класса доменом приложения, необходимо вызвать отладчик `SetEnableCustomNotification` для каждого домена приложений в процессе, если требуется получать уведомления из всего процесса.  
  
 Начиная с .NET Framework 4, только поддерживаемые это уведомление зависимости между потоками.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
