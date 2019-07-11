---
title: Метод IHostThreadPoolManager::SetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c79f18c1deec4183a5a736c5acf88e9a1fd8021
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749095"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a>Метод IHostThreadPoolManager::SetMinThreads
Задает минимальное количество свободных потоков, которые необходимо поддерживать узел обработки запросов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `MinThreads`  
 [in] Новый минимальное число потоков, которые необходимо поддерживать узла.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetMinThreads` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не поддерживает реализацию `SetMinThreads`.|  
  
## <a name="remarks"></a>Примечания  
 Узел не требуется предоставлять реализацию метода `SetMinThreads`. В этом случае он должен возвращать значение HRESULT E_NOTIMPL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [Метод GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [Метод SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [Интерфейс IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
