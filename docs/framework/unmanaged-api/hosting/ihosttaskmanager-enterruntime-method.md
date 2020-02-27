---
title: Метод IHostTaskManager::EnterRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: 94ad0073678e88e15d4b083793dca1423130f7e9
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628090"
---
# <a name="ihosttaskmanagerenterruntime-method"></a>Метод IHostTaskManager::EnterRuntime
Уведомляет узел о том, что вызов неуправляемого метода, например метода вызова платформы, возвращает управление выполнением среде CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`EnterRuntime` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для завершения запрошенного выделения.|  
  
## <a name="remarks"></a>Remarks  
 `EnterRuntime` вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов метода [леаверунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) , завершила выполнение, и возвращает управление выполнением среде выполнения.  
  
> [!NOTE]
> [Реверсинтеррунтиме](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) вызывается для уведомления узла о том, что неуправляемая функция, для которой был выполнен предыдущий вызов `LeaveRuntime`, делает вызов управляемого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Расширенное COM-взаимодействие](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Метод LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
