---
title: 'ICorProfilerInfo8:: Жетдинамикфунктионинфо'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 90246ade67f797c04f0da5d9a68dadb83e4ce418
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973864"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>Метод ICorProfilerInfo8:: Жетдинамикфунктионинфо
  
 Извлекает сведения о динамических методах.
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор функции, для которой требуется получить сведения.  

 `moduleId`  
 окне Указатель на модуль, в котором определен родительский класс функции.  
  
 `ppvSig`  
 заполняет Указатель на сигнатуру для функции.  
  
 `pbSig`  
 заполняет Указатель на число байтов для сигнатуры функции.
  
 `cchName`  
 [in] Максимальный размер массива `wszName`.
  
 `pcchName`  
 заполняет Число символов в `wszName` массиве.

 `wszName` \
 заполняет Массив `WCHAR` , содержащий имя функции, если таковое существует.
  
## <a name="remarks"></a>Примечания  
 Некоторые методы, такие как заглушки IL или LCG, не имеют связанных метаданных, которые можно извлечь с помощью интерфейсов API [IMetaDataImport](../metadata/imetadataimport-interface.md) и [IMetaDataImport2](../metadata/imetadataimport2-interface.md) . Такие методы могут быть обнаружены профилировщиками с помощью указателей инструкций или путем прослушивания [ICorProfilerCallback8::D инамикмесоджиткомпилатионстартед](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

 Этот API можно использовать для получения сведений о динамических методах, включая понятное имя, если оно доступно.  
  

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **.NET Framework версии:** [! ВКЛЮЧИТЬ[net_current_v472plus](../../../../includes/net-current-v472plus.md)  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

