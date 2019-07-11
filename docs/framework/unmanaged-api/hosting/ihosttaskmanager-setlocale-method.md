---
title: Метод IHostTaskManager::SetLocale
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f388a52c320c3f0d5f4ad7e073e1e8960d7947dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749368"
---
# <a name="ihosttaskmanagersetlocale-method"></a>Метод IHostTaskManager::SetLocale
Уведомляет ведущее приложение об изменении общеязыковой среды выполнения (CLR) языкового стандарта или языка и региональных параметров, в текущей выполняемой задаче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `lcid`  
 [in] Значения идентификатора языкового стандарта, сопоставляется только что назначенного географических языка и региональных параметров.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetLocale` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не поддерживает управляемый пользовательский код для изменения языкового стандарта.|  
  
## <a name="remarks"></a>Примечания  
 Среда выполнения вызывает `SetLocale` при значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> в управляемом коде изменяется свойство. Этот метод предоставляет возможность для узла выполнить какие-либо механизмы, которые он может иметь для синхронизации языковых стандартов. Если узел не поддерживает языковой стандарт, изменить из управляемого кода или не реализует механизм синхронизации языковых стандартов, она должна возвращать E_NOTIMPL из этого метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Метод SetUILocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
