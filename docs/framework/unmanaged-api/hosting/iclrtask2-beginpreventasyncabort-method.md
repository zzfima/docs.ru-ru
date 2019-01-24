---
title: Метод ICLRTask2::BeginPreventAsyncAbort
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a14a1cdbfebe4b1a15a17a1ad4e45c889737e394
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504168"
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
 Вызов этого метода увеличивает счетчик прерываний задержки потока для текущего потока на единицу.  
  
 Вызовы `BeginPreventAsyncAbort` и [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) могут быть вложенными. До тех пор, пока счетчик не равно нулю, являются отложенными прерывания потока для текущего потока. Если этот вызов не объединен с вызовом `EndPreventAsyncAbort` метод, можно достичь состояния, в каком потоке прерывания не удается доставить к текущему потоку.  
  
 Задержка не учитывается для потока, который прерывает сам.  
  
 Функциональные возможности, предоставляемые этой функции используется внутри виртуальной машины (VM). Неправильное использование этих методов может привести к непредсказуемому поведению в виртуальной Машине. Например, вызов `EndPreventAsyncAbort` без предварительного вызова функции `BeginPreventAsyncAbort` удалось задать счетчик до нуля, когда Виртуальная машина увеличит его. Аналогичным образом внутренний счетчик не проверяются на переполнение. Если оно превышает превышено, так как увеличивается на узле и виртуальной Машины, результирующее поведение не определено.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [Интерфейс ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
