---
title: Интерфейс IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e60b578256fb516ee0bd4edcec0b5a1a5179b46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54615339"
---
# <a name="ihostassemblymanager-interface"></a>Интерфейс IHostAssemblyManager
Предоставляет методы, которые позволяют ведущему приложению задать набор сборок, которые должны быть загружены с общеязыковой среды выполнения (CLR) или узлом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|Получает указатель интерфейса на [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , представляющий список сборок, загруженных приложением.|  
|[Метод GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|Получает указатель интерфейса на [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые, среда CLR для загрузки.|  
  
## <a name="remarks"></a>Примечания  
 Узел не нужно реализовать `IHostAssemblyManager` или `IHostAssemblyStore`. Если узел реализует `IHostAssemblyManager`, он также должен реализовать `IHostAssemblyStore`.  
  
 Среда выполнения запрашивает `IHostAssemblyManager` путем вызова [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) при инициализации с `IID` из IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [Интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
