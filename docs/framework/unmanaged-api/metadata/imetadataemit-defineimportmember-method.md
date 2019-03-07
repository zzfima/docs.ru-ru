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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ac44d29dd99e0205c515905f9846263033babf3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479302"
---
# <a name="imetadataemitdefineimportmember-method"></a>Метод IMetaDataEmit::DefineImportMember
Создает ссылку к указанному члену типа или модуль, который определен за пределами текущей области и определяет маркер для этой ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 [in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс, представляющий сборку, из которого импортируется целевому элементу.  
  
 `pbHashValue`  
 [in] Массив, содержащий хэш-код для сборки, определяемой параметром `pAssemImport`.  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 [in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс, который представляет область метаданных, из которого импортируется целевому элементу.  
  
 `mbMember`  
 [in] Токен метаданных, указывающее целевой член. Маркер может быть `mdMethodDef` (для метода-члена), `mdProperty` (для свойства элемента), или `mdFieldDef` (для поля члена) токена.  
  
 `pAssemEmit`  
 [in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) интерфейс, представляющий сборку, в который импортируется целевому элементу.  
  
 `tkParent`  
 [in] `mdTypeRef` Или `mdModuleRef` токена для типа или модуля, соответственно, которому принадлежит целевому элементу.  
  
 `pmr`  
 [out] `mdMemberRef` Маркер, который определен в текущей области для ссылки на член.  
  
## <a name="remarks"></a>Примечания  
 `DefineImportMember` Метод выполняет поиск элемента, определяемого `mbMember`, который определен в другой области, определяемой `pImport`и извлекает его свойства. Он использует эти сведения для вызова [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) метод в текущей области, чтобы создать ссылку на элемент.  
  
 Как правило, прежде чем использовать `DefineImportMember` метод, необходимо создать, в текущей области, ссылка на тип или ссылка на модуль для родительского класса, интерфейса или модуля целевого элемента. Маркер метаданных для этой ссылки затем передается в `tkParent` аргумент. Необходимо создать ссылку на родительский объект целевого члена, если она будет разрешена позже компилятора или компоновщика. Итоги вышесказанного приведены ниже.  
  
-   Если целевой член является полем или методом, используйте либо [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) или [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) метод, чтобы создать ссылку на тип, в текущей области, для родительский класс члена или родительского интерфейса.  
  
-   Если целевой член — это глобальная переменная или глобальная функция (то есть не является членом класса или интерфейса), используйте [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) метод для создания ссылки на модуль в текущей области, для родителя элемента модуль.  
  
-   Если родительский объект целевого члена будет разрешена позже компилятора или компоновщика, то передайте `mdTokenNil` в `tkParent`. Единственный сценарий, в котором применяется при глобальной функции или глобальной переменной импортируется из OBJ-файле, который в конечном счете будет связан с текущим модулем и слияние метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
