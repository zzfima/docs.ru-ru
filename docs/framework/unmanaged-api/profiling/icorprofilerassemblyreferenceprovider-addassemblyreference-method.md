---
title: Метод ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 762ebbe141473277dc064b36c6229f82d348f976
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582111"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a>Метод ICorProfilerAssemblyReferenceProvider::AddAssemblyReference
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Информирует общеязыковой среды выполнения (CLR) ссылки на сборку, которую профилировщик планирует добавить в [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 pAssemblyRefInfo  
 Указатель на [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) структуру, которая предоставляет среде CLR сведения о ссылку на сборку, которую ей следует учитывать при выполнении обхода замыкания.  
  
## <a name="remarks"></a>Примечания  
 Профилировщик вызывает этот метод для каждой целевой сборки, он планирует ссылаться из сборки, указанной в `wszAssemblyPath` аргумент [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) обратного вызова. [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) интерфейс объект передается в профилировщик [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) обратного вызова, а также путь к сборке и имени в `wszAssemblyPath` аргумент.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [Метод GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [Метод ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
