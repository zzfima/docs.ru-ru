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
ms.openlocfilehash: 5620df2ab2b2530332df02cf3f11a00d6b6c8fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostassemblystore-interface"></a>Интерфейс IHostAssemblyStore
Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Возвращает ссылку на сборку, которая не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) возвращается из вызова [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[Метод ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Разрешает модуль в сборку или связанный файл ресурсов (а не внедренные).|  
  
## <a name="remarks"></a>Примечания  
 `IHostAssemblyStore` предоставляет способ для узла для загрузки сборок, эффективно исходя из удостоверения сборки. Основное приложение загружает сборки, возвращая `IStream` экземпляры, которые указывают непосредственно на байты.  
  
 Среда CLR определяет реализовал ли узел `IHostAssemblyStore` путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` при инициализации. Это позволяет узлу, например, для управления с привязкой к пользовательским сборкам, но полагаются на среду выполнения для привязки к сборкам .NET Framework.  
  
> [!NOTE]
>  В реализации, предоставляя `IHostAssemblyStore`, узел указывает, ее планируется устранить все сборки, на которые не ссылается `ICLRAssemblyReferenceList` , возвращенные `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
>  .NET Framework версии 2.0 не предоставляет способ для узла для загрузки образа в машинном коде для сборки, в соответствии со [генератором машинных образов (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) программы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
