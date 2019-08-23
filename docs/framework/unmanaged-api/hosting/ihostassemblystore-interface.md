---
title: Интерфейс IHostAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f881440b2e93745723bd090cfbab0286dcd0a4e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937874"
---
# <a name="ihostassemblystore-interface"></a>Интерфейс IHostAssemblyStore
Предоставляет методы, позволяющие узлу загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Возвращает ссылку на сборку, на которую не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , возвращенную из вызова [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[Метод ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Разрешает модуль в сборке или в связанном (не внедренном) файле ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 `IHostAssemblyStore`Предоставляет узлу способ эффективного загрузки сборок на основе удостоверения сборки. Узел загружает сборки, возвращая `IStream` экземпляры, которые указывают непосредственно в байтах.  
  
 Среда CLR определяет, реализован `IHostAssemblyStore` ли узел путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` после инициализации. Это позволяет узлу, например, управлять привязкой к пользовательским сборкам, а также использовать среду выполнения для привязки к .NET Framework сборкам.  
  
> [!NOTE]
> При предоставлении реализации `IHostAssemblyStore`узел определяет его цель для разрешения всех сборок, на которые не ссылается объект `ICLRAssemblyReferenceList` , возвращенный из `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
> .NET Framework версии 2,0 не позволяет узлу загружать машинный образ сборки, как это предоставляется служебной программой [генератора образов в машинном код (Ngen. exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
