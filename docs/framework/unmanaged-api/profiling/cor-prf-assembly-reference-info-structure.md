---
title: Структура COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 380dbe43c09e0be48410431b87d796f502a7012b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634976"
---
# <a name="corprfassemblyreferenceinfo-structure"></a>Структура COR_PRF_ASSEMBLY_REFERENCE_INFO
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Обеспечивает среду CLR информацией о ссылке на сборку, которую ей следует учитывать при выполнении обхода замыкания.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|Указатель на открытый ключ или маркер сборки.|  
|`cbPublicKeyOrToken`|Количество байтов в открытом ключе или маркере.|  
|`szName`|Имя сборки, на которую дается ссылка.|  
|`pMetaData`|Указатель на метаданные сборки.|  
|`pbHashValue`|Указатель на хэшированный большой двоичный объект (BLOB).|  
|`cbHashValue`|Количество байтов в хэшированном BLOB.|  
|`dwAssemblyRefFlags`|Флаги сборки.|  
  
## <a name="remarks"></a>Примечания  
 Структура `COR_PRF_EX_CLAUSE_INFO` заполняется профилировщиком при его объявлении дополнительных ссылок на сборку, которые среда CLR должна учитывать при выполнении обхода замыкания.  
  
 Если профилировщик регистрирует [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) метод обратного вызова, среда выполнения передает путь и имя сборки для загрузки вместе с указателем на [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) объект интерфейса к этому методу. Затем профилировщик может вызвать [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) метод с `COR_PRF_ASSEMBLY_REFERENCE_INFO` объект для каждой целевой сборки, он планирует ссылаться из сборки, указанной в [ ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [Метод GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [Метод AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
