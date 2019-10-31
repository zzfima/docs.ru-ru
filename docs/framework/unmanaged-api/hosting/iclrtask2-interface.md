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
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124524"
---
# <a name="iclrtask2-interface"></a>Интерфейс ICLRTask2
Предоставляет все функциональные возможности интерфейса [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) ; Кроме того, предоставляет методы, которые позволяют задерживать прерывания потока в текущем потоке.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Откладывает запросы на прерывание нового потока в текущем потоке.|  
|[Метод EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Разрешает новые или ожидающие запросы на прерывание потока в результате прерывания потока в текущем потоке.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICLRTask2` наследует интерфейс `ICLRTask` и добавляет методы, позволяющие узлу откладывать прерывания потока, чтобы защитить область кода, которая не должна завершаться ошибкой. Вызов `BeginPreventAsyncAbort` увеличивает счетчик прерывания задержки потока для текущего потока, а вызов `EndPreventAsyncAbort` уменьшает его. Вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` могут быть вложенными. Пока значение счетчика больше нуля, прерывания потока для текущего потока откладываются.  
  
 Если вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` не связаны, можно достичь состояния, в котором прерывания потока не могут быть доставлены в текущий поток.  
  
 Задержка не учитывается для потока, который прерывает работу.  
  
 Функциональные возможности, предоставляемые этой функцией, используются внутри виртуальной машины (ВМ). Неправильное использование этих методов может привести к неопределенному поведению в виртуальной машине. Например, вызов `EndPreventAsyncAbort` без первого вызова `BeginPreventAsyncAbort` может установить нулевое значение счетчика, если виртуальная машина ранее увеличила ее. Аналогично, внутренний счетчик не проверяется на переполнение. Если он превышает его предельное значение, так как он увеличивается как узлом, так и виртуальной машиной, результирующее поведение не определено.  
  
 Сведения о членах, наследуемых от `ICLRTask` и о других применениях этого интерфейса, см. в разделе интерфейс [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
