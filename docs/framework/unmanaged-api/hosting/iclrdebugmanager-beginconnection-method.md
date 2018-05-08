---
title: Метод ICLRDebugManager::BeginConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1a285fca381195191def7612aef41c4bf72f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdebugmanagerbeginconnection-method"></a>Метод ICLRDebugManager::BeginConnection
Устанавливает новое соединение между узлом и отладчик, чтобы связать список задач с идентификатором и понятным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwConnectionId`  
 [in] Идентификатор для связи с список общих задач языка среды CLR.  
  
 `szConnectionName`  
 [in] Понятное имя, связанное со списком задач со средой CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`BeginConnection` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|`dwConnectionId` равно нулю, или `BeginConnection` уже был вызван с помощью этого `dwConnectionId` значение, или `szConnectionName` имел значение null.|  
|E_OUTOFMEMORY|Не хватает памяти может быть выделен для размещения в список задач, связанных с этим подключением.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), и [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), для связывания списки задач с идентификаторы и понятные имена.  
  
> [!IMPORTANT]
>  Эти три метода вызываются в определенном порядке для каждого набора задач. `BeginConnection` Сначала вызывается для установления нового подключения. `SetConnectionTasks` вызывается Далее необходимо предоставить набор задач, которые необходимо связать с подключением. `EndConnection` вызывается для удаления связи между списком задач и идентификатором и понятное имя. Однако вызовы других подключений могут быть вложенными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Интерфейс ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [Метод EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [Метод SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [Интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
