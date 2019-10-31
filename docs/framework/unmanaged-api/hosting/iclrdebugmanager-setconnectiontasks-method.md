---
title: Метод ICLRDebugManager::SetConnectionTasks
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
ms.openlocfilehash: d6092f16804fae39dd9496e8572edd64e1b7e9bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129373"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a>Метод ICLRDebugManager::SetConnectionTasks
Связывает список экземпляров [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) с идентификатором и понятным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `id`  
 окне Специфический для узла идентификатор соединения, с которым связывается массив `ppCLRTask`.  
  
 `dwCount`  
 окне Число членов `ppCLRTask`. Это число должно быть больше нуля.  
  
 `ppCLRTask`  
 окне Массив `ICLRTask`ных указателей, связываемых с соединением, идентифицируемым `id`. Этот массив должен содержать по крайней мере один элемент.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetConnectionTasks` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|[Бегинконнектион](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) не вызывался с помощью этого значения `id`или `dwCount` или `id` равно нулю, либо один из элементов `ppCLRTask` имеет значение null.|  
  
## <a name="remarks"></a>Заметки  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода: `BeginConnection`, `SetConnectionTasks`и [ендконнектион](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)для связывания списков задач с идентификаторами и понятными именами.  
  
> [!IMPORTANT]
> Эти три метода должны вызываться в определенном порядке для каждого набора задач. Сначала вызывается `BeginConnection`, чтобы установить новое соединение. `SetConnectionTasks` вызывается далее для предоставления набора задач, которые должны быть связаны с этим соединением. `EndConnection` вызывается Last для удаления связи между списком задач и идентификатором и понятным именем. Однако вызовы для различных соединений могут быть вложенными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [Метод BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [Метод EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [Интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
