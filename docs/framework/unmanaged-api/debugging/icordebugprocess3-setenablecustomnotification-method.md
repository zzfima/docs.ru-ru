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
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792465"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>Метод ICorDebugProcess3::SetEnableCustomNotification
Включает и отключает настраиваемые уведомления отладчика указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Параметры  
 `pClass`  
 окне Тип, указывающий пользовательские уведомления отладчика.  
  
 `fEnable`  
 [in] `true` включить пользовательские уведомления отладчика; `false`, чтобы отключить уведомления. Значение по умолчанию — `false`.  
  
## <a name="remarks"></a>Заметки  
 Если `fEnable` имеет значение `true`, вызовы метода <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> активируют обратный вызов [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) . По умолчанию уведомления отключены. Поэтому в отладчике должны быть указаны все типы уведомлений, о которых он знает, и требуется его обработку. Поскольку класс [ICorDebugClass](icordebug-interface.md) ограничивается доменом приложения, отладчик должен вызвать `SetEnableCustomNotification` для каждого домена приложения в процессе, если он хочет получить уведомление во всем процессе.  
  
 Начиная с .NET Framework 4, единственным поддерживаемым уведомлением является уведомление о зависимости между потоками.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugProcess3](icordebugprocess3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
