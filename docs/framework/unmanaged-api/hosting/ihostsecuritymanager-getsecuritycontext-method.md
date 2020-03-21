---
title: Метод IHostSecurityManager::GetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176257"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a>Метод IHostSecurityManager::GetSecurityContext
Получает запрошенный [IHostSecurityКонтекст](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) от хоста.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `eContextType`  
 (в) Одно из значений [EContextType,](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) указывающее, какой тип контекста безопасности вернуть.  
  
 `ppSecurityContext`  
 (ваут) Адрес указателя интерфейса `IHostSecurityContext` `eContextType`к .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetSecurityContext`вернулся успешно.|  
|HOST_E_CLRNOTAVAILABLE|Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. Когда метод возвращается E_FAIL, CLR больше не используется в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  
 Хост может управлять всем доступом к коду к токетонотам потока как по CLR, так и по пользовательскому коду. Он также может гарантировать, что полная информация о контексте безопасности передается через асинхронные операции или кодовые точки с ограниченным доступом к коду. `IHostSecurityContext`инкапсулирует эту информацию контекста безопасности, которая непрозрачна для CLR. CLR фиксирует эту информацию и перемещает ее по диспетчеризации элемента рабочего элемента пула потоков, выполнению окончательного элемента, а также конструкции модуля и класса.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисление EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
