---
title: Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788624"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock
Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppThread`  
 заполняет Управляемый поток, которому принадлежит блокировка монитора для этого объекта.  
  
 `pAcquisitionCount`  
 заполняет Количество случаев, в течение которых этот поток должен снять блокировку, прежде чем возвратить его в качестве владельца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|S_FALSE|Ни один управляемый поток не владеет блокировкой монитора для этого объекта.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Заметки  
 Если управляемый поток владеет блокировкой монитора для этого объекта:  
  
- Метод возвращает S_OK.  
  
- Объект потока действителен до тех пор, пока поток не завершит работу.  
  
 Если ни один из управляемых потоков не владеет блокировкой монитора для этого объекта, `ppThread` и `pAcquisitionCount` не изменяются, а метод возвращает S_FALSE.  
  
 Если `ppThread` или `pAcquisitionCount` не является допустимым указателем, результат не определен.  
  
 Если возникает ошибка, которая не может определить, какой поток владеет блокировкой монитора для этого объекта, метод возвращает значение HRESULT, которое указывает на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
