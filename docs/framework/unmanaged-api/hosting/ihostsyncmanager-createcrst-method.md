---
title: Метод IHostSyncManager::CreateCrst
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 101a652aa77e587003fb7e773e00ba9b77461a06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441897"
---
# <a name="ihostsyncmanagercreatecrst-method"></a>Метод IHostSyncManager::CreateCrst
Создает объект критической секции для синхронизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppCrst`  
 [out] Указатель на адрес [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляр реализовано узлом, или значение null, если не удалось создать критической секции.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`CreateCrst` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Не хватает памяти была доступна для создания запрошенной критической секции.|  
  
## <a name="remarks"></a>Примечания  
 Объекты критической секции обеспечивают синхронизацию аналогичны предоставляемым объект мьютекса, за исключением того, что критические секции могут использоваться только потоками одного процесса. `CreateCrst` зеркально отражает Win32 `InitializeCriticalSection` функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Интерфейс IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Интерфейс IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [Мьютексы](../../../../docs/standard/threading/mutexes.md)  
 [Классы Semaphore и SemaphoreSlim](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
