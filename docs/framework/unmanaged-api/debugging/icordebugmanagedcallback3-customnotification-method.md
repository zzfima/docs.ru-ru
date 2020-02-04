---
title: Метод ICorDebugManagedCallback3::CustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: 078f90387a475559067d402610ec264f4076ae01
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793254"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>Метод ICorDebugManagedCallback3::CustomNotification
Указывает, что было создано пользовательское уведомление отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a>Параметры  
 `pThread`  
 окне Указатель на поток, создавший уведомление.  
  
 `pAppDomain`  
 окне Указатель на домен приложения, содержащий поток, вызвавший уведомление.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Заметки  
 Последующий вызов метода [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) извлекает объект потока, который был передан методу <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>. Тип объекта потока должен быть ранее включен путем вызова метода [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) . Отладчик может считывать параметры конкретного типа из полей объекта потока и может сохранять ответы в полях.  
  
 Интерфейс [ICorDebug](icordebug-interface.md) не накладывает политики на типы уведомлений или их содержимое, а семантика уведомлений является строго контрактом между отладчиками, приложениями и .NET Framework.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
