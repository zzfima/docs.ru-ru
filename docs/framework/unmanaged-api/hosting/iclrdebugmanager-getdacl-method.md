---
title: Метод ICLRDebugManager::GetDacl
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
ms.openlocfilehash: a18e1efd246b0d6895d18ae0e7089a78703eae0e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129426"
---
# <a name="iclrdebugmanagergetdacl-method"></a>Метод ICLRDebugManager::GetDacl
Этот метод не реализован.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppacl`  
 заполняет Указатель интерфейса на список управления доступом (ACL).  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|E_NOTIMPL|Метод не реализован.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [Метод SetDacl](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)
- [Интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
