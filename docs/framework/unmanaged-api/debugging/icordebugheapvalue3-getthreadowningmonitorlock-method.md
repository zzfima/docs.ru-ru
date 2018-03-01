---
title: "Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1a2198e54c764fde0248563b040ac98984001888
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>Метод ICorDebugHeapValue3::GetThreadOwningMonitorLock
Возвращает управляемый поток, который владеет блокировкой монитора на этот объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppThread`  
 [out] Управляемый поток владеет блокировкой монитора на этот объект.  
  
 `pAcquisitionCount`  
 [out] Количество раз, этот поток будет необходимо снять блокировку перед возвратом монитором.  
  
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
  
-   Объект потока действителен до завершения потока.  
  
 Если нет управляемого потока, владеющего блокировкой монитора на этот объект `ppThread` и `pAcquisitionCount` не изменяются, и метод возвращает значение S_FALSE.  
  
 Если `ppThread` или `pAcquisitionCount` не является допустимым указателем, результат будет неопределенным.  
  
 При возникновении ошибки таким образом, что он не может определить, какие при его наличии, поток владеет блокировкой монитора на этот объект, метод возвращает значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
