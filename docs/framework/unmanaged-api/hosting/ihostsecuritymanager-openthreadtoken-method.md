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
ms.openlocfilehash: 2ced153798355aff882f0244f3dd946c39dea2bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121467"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>Метод IHostSecurityManager::OpenThreadToken
Открывает маркер доступа на уровне пользователей, связанный с выполняющимся в данный момент потоком.  
  
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
 окне Маска значений доступа, указывающих запрошенные типы доступа к токену потока. Эти значения определены в функции Win32 `OpenThreadToken`. Запрошенные типы доступа согласовываются с избирательным списком управления доступом (DACL) маркера, чтобы определить, какие типы доступа следует предоставить или запретить.  
  
 `bOpenAsSelf`  
 [in] `true`, чтобы указать, что проверка доступа должна выполняться с помощью контекста безопасности процесса для вызывающего потока; `false`, чтобы указать, что проверку доступа следует выполнять с помощью контекста безопасности для самого вызывающего потока. Если поток олицетворяет клиента, контекст безопасности может быть таким же, как у клиентского процесса.  
  
 `phThreadToken`  
 заполняет Указатель на вновь открытый маркер доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 `IHostSecurityManager::OpenThreadToken` ведет себя аналогично соответствующей функции Win32 с тем же именем, за исключением того, что функция Win32 позволяет вызывающему объекту передать обработчик произвольному потоку, тогда как `IHostSecurityManager::OpenThreadToken` открывает только маркер, связанный с вызывающим потоком.  
  
 Тип `HANDLE` не совместим с COM, то есть его размер зависит от операционной системы и требует настраиваемого маршалирования. Таким же маркер предназначен только для использования внутри процесса между средой CLR и узлом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
