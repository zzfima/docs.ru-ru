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
ms.openlocfilehash: f9995fda70d1d5a3c19c30496de6c32f20015d47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefineimportmember-method"></a>Метод IMetaDataEmit::DefineImportMember
Создает ссылку на указанный член типа или модуля, определенные вне текущей области видимости, а также определяет маркер для этой ссылки.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `pAssemImport`  
 [in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс, который представляет сборки, из которого импортируется целевого элемента.  
  
 `pbHashValue`  
 [in] Массив, содержащий хэш-код для сборки, определяемой параметром `pAssemImport`.  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 [in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс, представляющий область метаданных, из которого импортируется целевого элемента.  
  
 `mbMember`  
 [in] Токен метаданных, который определяет целевой элемент. Токен может быть `mdMethodDef` (для метода-члена), `mdProperty` (для свойства элемента) или `mdFieldDef` (для члена поля) токена.  
  
 `pAssemEmit`  
 [in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) интерфейс, представляющий сборку, в который импортируется целевого элемента.  
  
 `tkParent`  
 [in] `mdTypeRef` Или `mdModuleRef` токена для типа или модуля, соответственно, которому принадлежит целевой элемент.  
  
 `pmr`  
 [out] `mdMemberRef` Маркер, который определен в текущей области для ссылки на член.  
  
## <a name="remarks"></a>Примечания  
 `DefineImportMember` Метод выполняет поиск элемента, определяемого `mbMember`, который определен в другой области, определяемой `pImport`и извлекает его свойства. Она использует эти сведения для вызова [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) метод в текущей области, чтобы создать ссылку на элемент.  
  
 Как правило, перед использованием `DefineImportMember` метод, необходимо создать, в текущей области видимости, ссылку на тип или ссылку на модуль для родительского класса, интерфейса или модуля целевого элемента. Токен метаданных для этой ссылки передается в `tkParent` аргумент. Необходимо создать ссылку на родительский объект целевого члена, если он будет разрешен более поздней версии компилятора или компоновщика. Подведение итогов.  
  
-   Если целевой элемент поля или метода, используйте либо [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) или [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) метод, чтобы создать ссылку на тип, в текущей области для родительский класс или интерфейс родительского члена.  
  
-   Если целевой элемент — это глобальная переменная или глобальная функция (то есть, не является членом класса или интерфейса), используйте [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) метод для создания ссылки на модуль в текущей области для родительского элемента данного элемента модуль.  
  
-   Если родительский объект целевого члена будет разрешена позже компилятора или компоновщика, то передайте `mdTokenNil` в `tkParent`. Единственный сценарий, в котором применяется при глобальная функция или глобальная переменная импортируется из OBJ-файл, который в конечном счете будет связан с текущим модулем и объединенными метаданными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
