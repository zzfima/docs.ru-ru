---
title: Метод IHostTaskManager::CallNeedsHostHook
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176296"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>Метод IHostTaskManager::CallNeedsHostHook
Позволяет хосту указать, может ли время выполнения общего языка (CLR) ввести указанный вызов в неуправляемую функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `target`  
 (в) Адрес в отображенный портативный исполняемый (PE) файл неуправляемой функции, которая должна быть вызвана.  
  
 `pbCallNeedsHostHook`  
 (ваут) Указатель на значение Boolean, которое указывает, требует ли хост крючковатого вызова.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook`вернулся успешно.|  
|HOST_E_CLRNOTAVAILABLE|CLR не был загружен в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. Когда метод возвращается E_FAIL, CLR больше не используется в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  
 Чтобы оптимизировать выполнение кода, CLR выполняет анализ каждой платформы вызова вызова во время компиляции, чтобы определить, можно ли выполнить вызов. `CallNeedsHostHook`позволяет хосту переопределить это решение, требуя, чтобы вызов неуправляемой функции был подключен. Если хост требует сяткр, время выполнения не встраиваемый вызов.  
  
 Как правило, хосту потребуется крючок, в котором он должен настроить состояние плавающей точки, или при получении уведомления о том, что вызов входит в состояние, в котором хост не может отслеживать запросы на память во время выполнения или любые блокировки. Когда хост требует, чтобы вызов был подключен, время выполнения уведомляет множество переходов к управляемому коду и из его, используя вызовы [enterRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) [LeaveRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)и [ReverseLeaveRuntime.](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
