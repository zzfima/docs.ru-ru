---
title: Метод IMetaDataEmit::DefineImportType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 5b4b0682b2bddff96cb3d720900ed3aa39f06f9d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431847"
---
# <a name="imetadataemitdefineimporttype-method"></a>Метод IMetaDataEmit::DefineImportType
Создает ссылку на указанный тип, определенный вне текущей области, и определяет маркер для этой ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAssemImport`  
 окне Интерфейс [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) , представляющий сборку, из которой импортируется целевой тип.  
  
 `pbHashValue`  
 окне Массив, содержащий хэш для сборки, заданной `pAssemImport`.  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 окне Интерфейс [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) , представляющий область метаданных, из которой импортируется целевой тип.  
  
 `tdImport`  
 окне Токен `mdTypeDef`, указывающий тип целевого объекта.  
  
 `pAssemEmit`  
 окне Интерфейс [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) , представляющий сборку, в которую импортируется целевой тип.  
  
 `ptr`  
 заполняет Токен `mdTypeRef`, определенный в текущей области для ссылки на тип.  
  
## <a name="remarks"></a>Примечания  
 Перед вызовом метода [IMetaDataEmit::D ефинеимпортмембер](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) можно использовать метод `DefineImportType` для создания ссылки на тип в текущей области для родительского класса члена или родительского интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
