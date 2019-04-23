---
title: Метод ICLRSyncManager::CreateRWLockOwnerIterator
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c742410da8e7dbce53b53978516ab94243455849
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217553"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>Метод ICLRSyncManager::CreateRWLockOwnerIterator
Запросы, которые среда CLR (CLR) создают итератор для узла для определения набора задач, ожидающих блокировки чтения и записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cookie`  
 [in] Файл cookie, связанный с блокировкой требуемой чтения записи.  
  
 `pIterator`  
 [out] Указатель на итератор, который может быть передан [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) и [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) методы.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator` был вызван в потоке, который выполняется в данный момент управляемого кода.|  
  
## <a name="remarks"></a>Примечания  
 Обычно вызывать узлы `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, и `GetRWLockOwnerNext` методов во время обнаружения взаимоблокировок. Узел отвечает за то, что блокировка чтения или записи действительна, так как среда CLR не предпринимает попытки сохранения блокировка чтения или записи. Несколько стратегий доступны для узла обеспечить правильность блокировки:  
  
-   Узел может блокировать вызовы снятия блокировки чтения и записи (например, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) гарантией того, что этот блок не приводит к взаимоблокировке.  
  
-   Узел может блокировать выход из режима ожидания для объекта события, связанного с блокировкой чтения записи, еще раз, гарантируя, что этот блок не приводит к взаимоблокировке.  
  
> [!NOTE]
>  `CreateRWLockOwnerIterator` должен вызываться только в потоках, которые в данный момент неуправляемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
