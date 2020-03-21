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
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175867"
---
# <a name="imetadataemitdefineimportmember-method"></a>Метод IMetaDataEmit::DefineImportMember
Создает ссылку на указанный член типа или модуля, который определяется вне текущей области, и определяет маркер для этой ссылки.  
  
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
 (в) [Интерфейс IMetaDataAssemblyImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) представляющий сборку, из которой импортируется целевой элемент.  
  
 `pbHashValue`  
 (в) Массив, содержащий хэш для сборки, `pAssemImport`указанный .  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 (в) Интерфейс [IMetaDataImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) представляющий область метаданных, из которой импортируется целевой элемент.  
  
 `mbMember`  
 (в) Токен метаданных, опозначавший целевой символ. Токен может быть `mdMethodDef` (для элемента) `mdProperty` (для свойства `mdFieldDef` участника) или (для поля участника) маркера.  
  
 `pAssemEmit`  
 (в) Интерфейс [IMetaDataAssemblyEmit,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) представляющий сборку, в которую импортируется целевой элемент.  
  
 `tkParent`  
 (в) `mdTypeRef` Токен `mdModuleRef` или токен для типа или модуля, соответственно, который владеет целевым членом.  
  
 `pmr`  
 (ваут) Токен, `mdMemberRef` определяемый в текущей области для ссылки участника.  
  
## <a name="remarks"></a>Remarks  
 Метод `DefineImportMember` ищет участника, `mbMember`указанного, который определяется в другой `pImport`области, указанной, и извлекает его свойства. Он использует эту информацию для вызова [метода IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) в текущей области для создания ссылки участника.  
  
 Как правило, перед `DefineImportMember` использованием метода необходимо создать в текущей области ссылку на тип или ссылку на модуль для родительского класса, интерфейса или модуля целевого члена. Токен метаданных для этой ссылки `tkParent` затем передается в аргументе. Вам не нужно создавать ссылку на родителей целевого участника, если она будет решена позже компилятором или связующим звеном. Итог:  
  
- Если целевой участник является полем или методом, используйте либо [IMetaDataEmit::DefineTypeRefByName,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) либо метод [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) для создания ссылки типа в текущем объеме для родительского класса или родительского интерфейса участника.  
  
- Если целевой участник является глобальной переменной или глобальной функцией (т.е. не является членом класса или интерфейса), используйте метод [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) для создания ссылки на модуль в текущей области для родительского модуля участника.  
  
- Если родитель целевого участника будет решен позже компилятором `mdTokenNil` `tkParent`или связующим, затем перейдите в . Единственный сценарий, при котором это применимо, это когда глобальная функция или глобальная переменная импортируется из файла .obj, который в конечном итоге будет связан с текущим модулем и объединены метаданными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
