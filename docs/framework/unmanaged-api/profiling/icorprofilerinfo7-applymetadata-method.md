---
title: 'Метод ICorProfilerInfo7:: ApplyMetaData'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: 00d9bef1e2b59a2d2207d1e343380e0e81bee848
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130352"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Метод ICorProfilerInfo7:: ApplyMetaData
[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]  
  
 Применяет метаданные, которые недавно задаются `IMetadataEmit::Define*` методами, к указанному модулю.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне Идентификатор модуля, метаданные которого были изменены.  
  
## <a name="remarks"></a>Заметки  
 Если изменения метаданных вносятся после обратного вызова [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) , необходимо вызвать этот метод перед использованием новых метаданных.  
  
 `ApplyMetaData` поддерживает добавление только следующих типов метаданных:  
  
- `AssemblyRef` записи, которые создаются путем вызова метода [IMetaDataAssemblyEmit::D ефинеассемблиреф](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md). метод.  
  
- `TypeRef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинетиперефбинаме](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) .  
  
- `TypeSpec` записи, которые создаются путем вызова метода [IMetaDataEmit:: жеттокенфромтипеспек](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) .  
  
- `MemberRef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинемемберреф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) .  
  
- `MemberSpec` записи, которые создаются путем вызова метода [IMetaDataEmit2::D ефинемесодспек](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) .  
  
- `UserString` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинеусерстринг](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .  

Начиная с .NET Core 3,0, `ApplyMetaData` также поддерживает следующие типы:

- `TypeDef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинетипедеф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) .

- `MethodDef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинемесод](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) . Однако добавление виртуальных методов в существующий тип не поддерживается. Виртуальные методы должны быть добавлены перед обратным вызовом [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
