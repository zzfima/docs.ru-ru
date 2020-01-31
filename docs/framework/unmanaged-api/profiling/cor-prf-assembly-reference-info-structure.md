---
title: Структура COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 4fdc8e1074bf45de3a8ab85500a85b124ce34fa1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867338"
---
# <a name="cor_prf_assembly_reference_info-structure"></a>Структура COR_PRF_ASSEMBLY_REFERENCE_INFO
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
  
## <a name="remarks"></a>Заметки  
 Структура `COR_PRF_EX_CLAUSE_INFO` заполняется профилировщиком при его объявлении дополнительных ссылок на сборку, которые среда CLR должна учитывать при выполнении обхода замыкания.  
  
 Если профилировщик регистрируется для метода обратного вызова [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , среда выполнения передает путь и имя загружаемой сборки вместе с указателем на объект интерфейса [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) для этого метода. Затем профилировщик может вызвать метод [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) с объектом `COR_PRF_ASSEMBLY_REFERENCE_INFO` для каждой целевой сборки, на которую планируется ссылаться из сборки, указанной в обратном вызове [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Структуры профилирования](profiling-structures.md)
- [Метод GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)
- [Метод AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
