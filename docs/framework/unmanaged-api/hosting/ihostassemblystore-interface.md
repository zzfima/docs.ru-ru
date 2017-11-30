---
title: "Интерфейс IHostAssemblyStore"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore
helpviewer_keywords: IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 284afbe73bea28a0aafe8d5e9e030c43be94aea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystore-interface"></a>Интерфейс IHostAssemblyStore
Предоставляет методы, позволяющие основному приложению загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[ProvideAssembly-метод](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|Возвращает ссылку на сборку, которая не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) возвращается из вызова [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).|  
|[ProvideModule-метод](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|Разрешает модуль в сборку или связанный файл ресурсов (а не внедренные).|  
  
## <a name="remarks"></a>Примечания  
 `IHostAssemblyStore`предоставляет способ для узла для загрузки сборок, эффективно исходя из удостоверения сборки. Основное приложение загружает сборки, возвращая `IStream` экземпляры, которые указывают непосредственно на байты.  
  
 Среда CLR определяет реализовал ли узел `IHostAssemblyStore` путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` при инициализации. Это позволяет узлу, например, для управления с привязкой к пользовательским сборкам, но полагаются на среду выполнения для привязки к сборкам .NET Framework.  
  
> [!NOTE]
>  В реализации, предоставляя `IHostAssemblyStore`, узел указывает, ее планируется устранить все сборки, на которые не ссылается `ICLRAssemblyReferenceList` , возвращенные `IHostAssemblyManager::GetNonHostStoreAssemblies`.  
  
> [!NOTE]
>  .NET Framework версии 2.0 не предоставляет способ для узла для загрузки образа в машинном коде для сборки, в соответствии со [генератором машинных образов (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) программы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRAssemblyReferenceList-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Ihostassemblymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
