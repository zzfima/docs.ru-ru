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
ms.openlocfilehash: 8ac1c18d094deca50d461ef9ff0933a4f87176e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132992"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>Метод IHostTaskManager::LeaveRuntime
Уведомляет основное приложение о том, что Текущая выполняемая задача собирается покинуть среду CLR, и введите неуправляемый код.  
  
> [!IMPORTANT]
> Соответствующий вызов [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) уведомляет основное приложение о том, что выполняемая в данный момент задача повторно вводит управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `target`  
 окне Адрес в сопоставленном переносимом исполняемом файле неуправляемой функции для вызова.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для завершения запрошенного выделения.|  
  
## <a name="remarks"></a>Заметки  
 Последовательности вызовов для и из неуправляемого кода могут быть вложенными. Например, приведенный ниже список описывает гипотетическую ситуацию, в которой последовательность вызовов `LeaveRuntime`, [IHostTaskManager:: реверсинтеррунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)и `IHostTaskManager::EnterRuntime` позволяет узлу опознать вложенные слои.  
  
|Действие|Вызов соответствующего метода|  
|------------|-------------------------------|  
|Управляемый исполняемый файл Visual Basic вызывает неуправляемую функцию, написанную на языке C, с помощью вызова неуправляемого кода.|`IHostTaskManager::LeaveRuntime`|  
|Неуправляемая функция C вызывает метод в управляемой библиотеке DLL, написанной C#в.|`IHostTaskManager::ReverseEnterRuntime`|  
|Управляемая C# функция вызывает другую неуправляемую функцию, написанную на языке C, также используя вызов неуправляемого кода.|`IHostTaskManager::LeaveRuntime`|  
|Вторая неуправляемая функция возвращает выполнение C# функции.|`IHostTaskManager::EnterRuntime`|  
|C# Функция возвращает выполнение в первую неуправляемую функцию.|`IHostTaskManager::ReverseLeaveRuntime`|  
|Первая неуправляемая функция возвращает выполнение в программу Visual Basic.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
