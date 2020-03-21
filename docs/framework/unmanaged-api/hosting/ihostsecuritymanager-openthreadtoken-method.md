---
title: Метод IHostSecurityManager::OpenThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176270"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>Метод IHostSecurityManager::OpenThreadToken
Открывает дискреционный маркер доступа, связанный с в настоящее время исполняющим потоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 (в) Маска значений доступа, которые указывают запрашиваемые типы доступа к маркеру потока. Эти значения определены в функции Win32. `OpenThreadToken` Запрошенные типы доступа согласовываются со списком управления дискреционным доступом токена (DACL), чтобы определить, какие типы доступа к предоставлению или отказу.  
  
 `bOpenAsSelf`  
 (в) `true` указать, что проверка доступа должна быть сделана с использованием контекста безопасности процесса для потока вызова; `false` указать, что проверка доступа должна быть выполнена с использованием контекста безопасности для самого потока вызова. Если поток выдает себя за клиента, контекст безопасности может быть контекстом процесса клиента.  
  
 `phThreadToken`  
 (ваут) Указатель на недавно открытый токен доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`вернулся успешно.|  
|HOST_E_CLRNOTAVAILABLE|Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. Когда метод возвращается E_FAIL, CLR больше не используется в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  
 `IHostSecurityManager::OpenThreadToken`ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция `IHostSecurityManager::OpenThreadToken` Win32 позволяет абоненту передавать в ручку произвольному потоку, в то время как открывается только маркер, связанный с потоком вызова.  
  
 Тип `HANDLE` не соответствует COM, то есть его размер специфичен для операционной системы, и он требует пользовательского маршалинга. Таким образом, этот маркер предназначен для использования только в процессе, между CLR и хостом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
