---
title: Метод IMetaDataEmit::DefineImportMember
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: 75711b3d87699ff5db21a04351ff0acaccabb5aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431858"
---
# <a name="imetadataemitdefineimportmember-method"></a>Метод IMetaDataEmit::DefineImportMember
Создает ссылку на указанный элемент типа или модуля, который определен за пределами текущей области, и определяет маркер для этой ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAssemImport`  
 окне Интерфейс [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) , представляющий сборку, из которой импортируется целевой элемент.  
  
 `pbHashValue`  
 окне Массив, содержащий хэш для сборки, заданной `pAssemImport`.  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 окне Интерфейс [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) , представляющий область метаданных, из которой импортируется целевой элемент.  
  
 `mbMember`  
 окне Токен метаданных, указывающий целевой элемент. Токен может быть `mdMethodDef` (для метода-члена), `mdProperty` (для свойства элемента) или маркера `mdFieldDef` (для поля члена).  
  
 `pAssemEmit`  
 окне Интерфейс [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) , представляющий сборку, в которую импортируется целевой элемент.  
  
 `tkParent`  
 окне Маркер `mdTypeRef` или `mdModuleRef` для типа или модуля соответственно, которому принадлежит целевой элемент.  
  
 `pmr`  
 заполняет Токен `mdMemberRef`, определенный в текущей области для ссылки на элемент.  
  
## <a name="remarks"></a>Заметки  
 Метод `DefineImportMember` ищет элемент, заданный `mbMember`, который определен в другой области, заданной `pImport`, и получает его свойства. Эта информация используется для вызова метода [IMetaDataEmit::D ефинемемберреф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) в текущей области для создания ссылки на элемент.  
  
 Как правило, перед использованием метода `DefineImportMember` необходимо создать в текущей области ссылку на тип или ссылку на модуль для родительского класса, интерфейса или модуля целевого элемента. Затем маркер метаданных для этой ссылки передается в аргумент `tkParent`. Не нужно создавать ссылку на родительский элемент целевого элемента, если он будет разрешен позже компилятором или компоновщиком. Подведение итогов.  
  
- Если целевой элемент является полем или методом, используйте метод [IMetaDataEmit::D ефинетиперефбинаме](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) или [IMetaDataEmit::D ефинеимпорттипе](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) для создания ссылки на тип в текущей области для родительского класса члена или родительского интерфейса.  
  
- Если целевой элемент является глобальной переменной или глобальной функцией (то есть не членом класса или интерфейса), используйте метод [IMetaDataEmit::D ефинемодулереф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) , чтобы создать ссылку на модуль в текущей области для родительского модуля элемента.  
  
- Если родительский элемент целевого элемента будет разрешен позже компилятором или компоновщиком, то передайте `mdTokenNil` в `tkParent`. Единственный сценарий, в котором это применимо, — это то, что глобальная функция или глобальная переменная импортируется из OBJ-файла, который в конечном итоге будет связан с текущим модулем и объединенными метаданными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
