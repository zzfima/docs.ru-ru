---
title: "Интерфейс ICLRTask2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f2312d193031eae556f55b061a36259531d013b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtask2-interface"></a>Интерфейс ICLRTask2
Предоставляет все функциональные возможности [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) интерфейс; Кроме того, предоставляет методы, позволяющие прерывания потоков, задержки в текущем потоке.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[BeginPreventAsyncAbort-метод](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Задержки новые запросы прерывания потока в текущем потоке.|  
|[EndPreventAsyncAbort-метод](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Позволяет новым или ожидающим запросам прерывания потока в результате поток прерывает выполнение в текущем потоке.|  
  
## <a name="remarks"></a>Примечания  
 `ICLRTask2` Интерфейс наследует `ICLRTask` интерфейс и добавляет методы, позволяющие основному приложению откладывать прерывания потока для защиты области кода, которая должна работать без сбоев. Вызов `BeginPreventAsyncAbort` увеличивает на единицу счетчик задержки прерывания для текущего потока, а вызов метода `EndPreventAsyncAbort` уменьшает его. Вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` могут быть вложенными. При условии, что значение счетчика больше нуля, задерживаются прерывания потока для текущего потока.  
  
 Если вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` , не связан, ее можно достичь состояния, в какой поток прерываний не доставляться к текущему потоку.  
  
 Задержка для потока, который прерывает сам не учитывается.  
  
 Функциональные возможности, предоставляемые этой функции используется внутренне для виртуальной машины (VM). Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине. Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его. Аналогичным образом внутренний счетчик не проверяется на переполнение. Если она превышает предельное значение целочисленного, так как увеличивается на узле и ВМ, результирующее поведение не определено.  
  
 Для сведения о членах наследуется от `ICLRTask` и о других вариантах использования этого интерфейса, в разделе [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
