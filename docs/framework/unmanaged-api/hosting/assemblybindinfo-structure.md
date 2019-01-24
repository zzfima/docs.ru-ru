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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0247f356bfc9f354edc420ea5460da02b17ab116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561144"
---
# <a name="assemblybindinfo-structure"></a>Структура AssemblyBindInfo
Содержит подробные сведения о сборке, на которую указывает ссылка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`dwAppDomainId`|Уникальный идентификатор для `IStream` возвращается путем вызова [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), из которой сборка будет необходимо загрузить.|  
|`lpReferencedIdentity`|Уникальный идентификатор для указанной сборки.|  
|`lpPostPolicyIdentity`|Идентификатор указанной ссылками сборки после применения всех значений политики привязки.|  
|`ePolicyLevel`|Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения, указывающие, какие политики управления версиями, если таковые имеются, применяются к указанной ссылками сборки.|  
  
## <a name="remarks"></a>Примечания  
 Узел предоставляет уникальный идентификатор `dwAppDomainId` для общеязыковой среды выполнения (CLR). После вызова `IHostAssemblyStore::ProvideAssembly` возвращает, среда выполнения использует идентификатор для определения ли содержимое `IStream` были сопоставлены. Если Да, среда выполнения загружает имеющуюся копию вместо повторного сопоставления потока. Среда выполнения также использует этот идентификатор ключа поиска для потоков, возвращаемых из вызовов [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md). Таким образом идентификатор должен быть уникальным для запросов модулей и запросов сборок.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.idl  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Интерфейс ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Интерфейс IHostAssemblyManager](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [Интерфейс IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [Структура ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
