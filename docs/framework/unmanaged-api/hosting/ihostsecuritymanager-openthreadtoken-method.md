---
title: "Метод IHostSecurityManager::OpenThreadToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.OpenThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d3b5ec31944b58bec6268de6e54503141880e6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a>Метод IHostSecurityManager::OpenThreadToken
Открывает маркер доступом, связанный с текущей выполняемой потоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwDesiredAccess`  
 [in] Маска доступа значений, указывающих запрошенных типов доступа к маркер потока. Эти значения определяются в Win32 `OpenThreadToken` функции. Запрошенные типы доступа сравниваются со списком управления доступом маркера (DACL), чтобы определить, какие типы доступа, чтобы предоставить или отменить.  
  
 `bOpenAsSelf`  
 [in] `true` для указания, что проверка доступа следует выполнить, используя контекст безопасности процесса для вызывающего потока; `false` для указания, что проверка доступа должны выполняться с использованием контекста безопасности для самого вызывающего потока. Если поток олицетворяет клиента, контекст безопасности может быть клиентского процесса.  
  
 `phThreadToken`  
 [out] Указатель на токен открытый доступ.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OpenThreadToken`успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `IHostSecurityManager::OpenThreadToken`ведет себя точно так же для соответствующей функции Win32 с таким же именем, за исключением того, что функция Win32 позволяет вызывающему объекту произвольном потоке, передается дескриптор, хотя `IHostSecurityManager::OpenThreadToken` открывает только маркером, связанным с вызывающего потока.  
  
 `HANDLE` Типа не удовлетворяет требованиям COM, то есть, его размер будет относится к операционной системе и требуется пользовательский маршалинг. Таким образом этот токен предназначен для использования только в пределах процесса в среде CLR и узла.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IHostSecurityContext-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
