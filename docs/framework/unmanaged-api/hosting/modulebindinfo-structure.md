---
title: "Структура ModuleBindInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ModuleBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ModuleBindInfo
helpviewer_keywords: ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6488503e0300530b22c0c6f904e11db7f5d5b41c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="modulebindinfo-structure"></a>Структура ModuleBindInfo
Предоставляет подробные сведения о модуле, на который указывает ссылка и сборки, содержащей его.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dwAppDomainId`|Уникальный идентификатор для `IStream` , возвращается путем вызова [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) метода, из которого производится загрузка модуля.|  
|`lpAssemblyIdentity`|Уникальный идентификатор сборки, содержащей модуль, на который указывает ссылка.|  
|`lpModuleName`|Имя модуля, на который указывает ссылка.|  
  
## <a name="remarks"></a>Примечания  
 `ModuleBindInfo`передается в качестве параметра `IHostAssemblyStore::ProvideModule`. Узел предоставляет уникальный идентификатор `dwAppDomainId` для общеязыковой среды выполнения (CLR). После вызова [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) метод возвращает управление, среда выполнения использует идентификатор, чтобы определить, является ли содержимое `IStream` были сопоставлены. В этом случае среда выполнения загружает имеющуюся копию вместо повторного сопоставления потока. Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов `IHostAssemblyStore::ProvideAssembly` метод. Таким образом идентификатор должен быть уникальным для запросов модулей также и для запросов сборок.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.idl  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Assemblybindinfo-структура](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [Iclrassemblyidentitymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [Ihostassemblymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
