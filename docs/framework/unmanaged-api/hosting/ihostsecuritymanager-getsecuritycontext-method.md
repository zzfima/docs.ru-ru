---
title: "Метод IHostSecurityManager::GetSecurityContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.GetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b150700c50842791a2413688583e7e1289852d62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a>Метод IHostSecurityManager::GetSecurityContext
Возвращает запрошенный [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) хоста.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `eContextType`  
 [in] Один из [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , указывающее, какой тип контекста безопасности для возврата значений.  
  
 `ppSecurityContext`  
 [out] Адрес указателя интерфейса `IHostSecurityContext` из `eContextType`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetSecurityContext`успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Узел может управлять доступом кода к маркерам потока из кода среды CLR и пользователя. Также можно обеспечить, полный безопасность Контекстная информация, передаваемая через асинхронные операции или кодовые точки с ограниченным доступом. `IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, являющиеся непрозрачными для среды CLR. Среда CLR перехватывает эту информацию и перемещает ее через операции подготовки к отправке элемента рабочего пула потоков, выполнения метода завершения и конструирование модулей и классов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Econtexttype-перечисление](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [IHostSecurityContext-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
