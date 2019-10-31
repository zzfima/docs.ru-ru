---
title: Структура AssemblyBindInfo
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 8764a3d665c997460419561eb168f92ca769c30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192110"
---
# <a name="assemblybindinfo-structure"></a>Структура AssemblyBindInfo
Предоставляет подробные сведения о сборке, на которую указывает ссылка.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dwAppDomainId`|Уникальный идентификатор `IStream`, возвращаемого вызовом метода [IHostAssemblyStore::P ровидеассембли](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), из которого загружается сборка, на которую указывает ссылка.|  
|`lpReferencedIdentity`|Уникальный идентификатор сборки, на которую указывает ссылка.|  
|`lpPostPolicyIdentity`|Идентификатор сборки, на которую указывает ссылка, после применения любых значений политики привязки.|  
|`ePolicyLevel`|Одно из значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , указывающее, какие политики управления версиями должны применяться к сборке, на которую указывает ссылка.|  
  
## <a name="remarks"></a>Заметки  
 Узел предоставляет уникальный идентификатор, `dwAppDomainId` общеязыковой среде выполнения (CLR). После того как вызов `IHostAssemblyStore::ProvideAssembly` возвращает, среда выполнения использует идентификатор, чтобы определить, сопоставлено ли содержимое `IStream`. Если это так, среда выполнения загружает существующую копию вместо повторного сопоставления потока. Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов [IHostAssemblyStore::P ровидемодуле](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Таким образом, идентификатор должен быть уникальным для запросов модуля и для запросов сборки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. idl  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Интерфейс ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [Структура ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
