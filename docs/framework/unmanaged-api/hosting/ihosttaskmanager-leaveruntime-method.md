---
title: Метод IHostTaskManager::LeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d31c5c1b95d250f90b202b391d908f9c12afb84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>Метод IHostTaskManager::LeaveRuntime
Уведомляет узел, что текущая выполняющаяся задача собирается оставьте общеязыковой среды выполнения (CLR) и введите неуправляемого кода.  
  
> [!IMPORTANT]
>  С соответствующим вызовом [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) уведомляет узел, что текущая выполняющаяся задача повторный ввод управляемого кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `target`  
 [in] Адрес в пределах сопоставленных переносимый исполняемый файл для вызова неуправляемой функции.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для завершения запрошенной распределения.|  
  
## <a name="remarks"></a>Примечания  
 Последовательность вызовов в и из неуправляемого кода могут быть вложенными. Например, в следующем списке представлены гипотетическую ситуацию, в котором последовательность вызовов `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), и `IHostTaskManager::EnterRuntime` предоставляет узлу возможность определить вложенные слои.  
  
|Действие|Вызов соответствующего метода|  
|------------|-------------------------------|  
|Вызвать неуправляемую функцию, написанную на языке C с помощью платформы управляемых исполняемая программа вызывает Visual Basic.|`IHostTaskManager::LeaveRuntime`|  
|Неуправляемые функции C вызывает метод в управляемой библиотеке DLL, написанные на C#.|`IHostTaskManager::ReverseEnterRuntime`|  
|Управляемые функции C# вызывает другую неуправляемую функцию, написанную на языке C, также вызове неуправляемого кода.|`IHostTaskManager::LeaveRuntime`|  
|Второй неуправляемая функция возвращает выполнение функции C#.|`IHostTaskManager::EnterRuntime`|  
|Функция C# возвращает результаты выполнения первой неуправляемой функции.|`IHostTaskManager::ReverseLeaveRuntime`|  
|Первая неуправляемая функция возвращает выполнение программы на Visual Basic.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
