---
title: Структура ModuleBindInfo
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133752"
---
# <a name="modulebindinfo-structure"></a>Структура ModuleBindInfo
Предоставляет подробные сведения о модуле, на который указывает ссылка, и содержащей его сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dwAppDomainId`|Уникальный идентификатор `IStream`, возвращаемый вызовом метода [IHostAssemblyStore::P ровидемодуле](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) , из которого загружается указанный модуль.|  
|`lpAssemblyIdentity`|Уникальный идентификатор сборки, содержащей упоминаемый модуль.|  
|`lpModuleName`|Имя модуля, на который указывает ссылка.|  
  
## <a name="remarks"></a>Заметки  
 `ModuleBindInfo` передается в качестве параметра `IHostAssemblyStore::ProvideModule`. Узел предоставляет уникальный идентификатор, `dwAppDomainId` общеязыковой среде выполнения (CLR). После вызова метода [IHostAssemblyStore::P ровидеассембли](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) среда выполнения использует идентификатор, чтобы определить, сопоставлено ли содержимое `IStream`. Если это так, среда выполнения загружает существующую копию вместо повторного сопоставления потока. Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов метода `IHostAssemblyStore::ProvideAssembly`. Таким образом, идентификатор должен быть уникальным для запросов модуля, а также для запросов сборки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Структура AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [Интерфейс ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
