---
title: Метод ICorProfilerCallback6::GetAssemblyReferences
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a705257c150fe0272674c08c7b316ab968766cb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475343"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a>Метод ICorProfilerCallback6::GetAssemblyReferences
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszAssemblyPath`  
 [в] Путь и имя сборки, метаданные которой будут изменены.  
  
 `pAsmRefProvider`  
 [in] Указатель на адрес [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) ссылается на интерфейс, который указывает сборку для добавления.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значения, возвращаемые из этого обратного вызова, игнорируются.  
  
## <a name="remarks"></a>Примечания  
 Этот обратный вызов управляется заданием [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) флага маски события при вызове [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метод. Если профилировщик регистрирует [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) метод обратного вызова, среда выполнения передает путь и имя сборки для загрузки вместе с указателем на [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) объект интерфейса к этому методу. Затем профилировщик может вызвать [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) метод с `COR_PRF_ASSEMBLY_REFERENCE_INFO` объект для каждой целевой сборки, он планирует ссылаться из сборки, указанной в `GetAssemblyReferences` обратный вызов.  
  
 Используйте обратный вызов `GetAssemblyReferences`, только если для добавления ссылок на сборку профилировщик должен изменить метаданные сборки. (Но Обратите внимание, что фактическое изменение метаданных сборки выполняется в [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)метод обратного вызова.) Профилировщику следует реализовать метод обратного вызова `GetAssemblyReferences`, чтобы сообщить среде CLR о том, что ссылки на сборку будут добавлены после загрузки модуля.  Это гарантирует, что решения о предоставлении общего доступа к сборке, сделанные средой CLR во время этой ранней стадии, остаются в силе, хотя позже профилировщик планирует изменить ссылки на сборку метаданных.  Это поможет избежать некоторых случаев, при которых модификации метаданных профилировщика приводят к ошибке `SECURITY_E_INCOMPATIBLE_SHARE`.  
  
 Профилировщик использует [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) объект, предоставленный этим методом для добавления ссылки на сборки для обхода замыкания ссылки на сборки среды CLR.  [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) объекта следует использовать только внутри этого обратного вызова. Вызовы [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) метод из этого обратного вызова не вызывают изменение метаданных, но только в измененных обхода замыкания. Профилировщик все равно придется использовать [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) для прямого добавления ссылок на сборки изнутри [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова для ссылки на сборки, даже если он реализует `GetAssemblyReferences` обратного вызова.  
  
 Профилировщик должен быть готовы к получению повторяющиеся вызовы на этот обратный вызов для той же сборке и одинаково отвечать на каждый такой дублированный вызов (сделав тот же набор [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) вызовов).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)
- [Метод ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [Структура COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
- [Интерфейс ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
