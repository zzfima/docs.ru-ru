---
title: "Метод ICLRTask2::BeginPreventAsyncAbort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2.BeginPreventAsyncAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33136dfbfa8bb3e0147bc1a1c1bb9e88ab2e4239
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>Метод ICLRTask2::BeginPreventAsyncAbort
Новый поток задержки запросов в прерывания потока в текущем потоке прерывания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION|Метод был вызван для потока, который не является текущим потоком.|  
  
## <a name="remarks"></a>Примечания  
 Вызов этого метода увеличивает счетчик задержки прерывания для текущего потока на единицу.  
  
 Вызовы `BeginPreventAsyncAbort` и [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) могут быть вложенными. При условии, что значение счетчика больше нуля, задерживаются прерывания потока для текущего потока. Если этот вызов не связан с помощью вызова `EndPreventAsyncAbort` метод, его можно достичь состояния, в какой поток прерываний не доставляться к текущему потоку.  
  
 Задержка для потока, который прерывает сам не учитывается.  
  
 Функциональные возможности, предоставляемые этой функции используется внутренне для виртуальной машины (VM). Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине. Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его. Аналогичным образом внутренний счетчик не проверяется на переполнение. Если она превышает предельное значение целочисленного, так как увеличивается на узле и ВМ, результирующее поведение не определено.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [EndPreventAsyncAbort-метод](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)  
 [ICLRTask2-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [ICLRTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
