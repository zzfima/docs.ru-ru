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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 361cc3b897b4c85297b597f80aaffc2a2760f88e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468485"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock
Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppThread`  
 [out] Управляемый поток, которому принадлежит блокировка монитора для этого объекта.  
  
 `pAcquisitionCount`  
 [out] Количество раз, этот поток необходимо снять блокировку, прежде чем он возвращается монитором.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|S_FALSE|Не управляемый поток владеет блокировкой монитора на этот объект.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
 Если управляемый поток владеет блокировкой монитора на этот объект:  
  
-   Метод возвращает значение S_OK.  
  
-   Поток выходит из объекта потока остается действительным.  
  
 Если не управляемый поток владеет блокировкой монитора на этот объект `ppThread` и `pAcquisitionCount` ничем не отличаются, и метод возвращает значение S_FALSE.  
  
 Если `ppThread` или `pAcquisitionCount` не является допустимым указателем, результат не определен.  
  
 При возникновении ошибки таким образом, что не удается определить, который, если таковые имеются, поток владеет блокировкой монитора на этот объект, метод возвращает значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
