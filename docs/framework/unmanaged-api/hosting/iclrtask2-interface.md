---
title: Интерфейс ICLRTask2
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518248651de6d8afdf25692c5f48da52b11eb0f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763403"
---
# <a name="iclrtask2-interface"></a>Интерфейс ICLRTask2
Предоставляет все функциональные возможности [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) интерфейс; Кроме того, предоставляет методы, позволяющие прерывания потоков, задержки в текущем потоке.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Задержки новые запросы прерывания потока в текущем потоке.|  
|[Метод EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Позволяет новым или ожидающих запросов прерывания потока с последующим получением поток прерывает выполнение в текущем потоке.|  
  
## <a name="remarks"></a>Примечания  
 `ICLRTask2` Интерфейс наследует `ICLRTask` интерфейс и добавляет методы, позволяющие основному приложению задерживать аварийные завершения потоков, для защиты области кода, который должен работать без сбоев. Вызов `BeginPreventAsyncAbort` увеличивает значение счетчика прерываний задержки потока для текущего потока и вызова `EndPreventAsyncAbort` уменьшает его. Вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` могут быть вложенными. До тех пор, пока счетчик не равно нулю, являются отложенными прерывания потока для текущего потока.  
  
 Если вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` находятся не в паре, это можно достичь состояния, в каком потоке прерывания не доставляться к текущему потоку.  
  
 Задержка не учитывается для потока, который прерывает сам.  
  
 Функциональные возможности, предоставляемые этой функции используется внутри виртуальной машины (VM). Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине. Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его. Аналогичным образом внутренний счетчик не проверяются на переполнение. Если оно превышает превышено, так как увеличивается на узле и виртуальной Машины, результирующее поведение не определено.  
  
 Сведения об элементах, наследуемого от `ICLRTask` и о других вариантах использования этого интерфейса, см. в разделе [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
