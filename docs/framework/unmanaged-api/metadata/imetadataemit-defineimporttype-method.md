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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68e6f7599db55ed9429f159b380a8a9f8ae3f034
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefineimporttype-method"></a>Метод IMetaDataEmit::DefineImportType
Создает ссылку для указанного типа, определенные вне текущей области видимости, а также определяет маркер для этой ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `pAssemImport`  
 [in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс, который представляет сборки, из которого импортируется в целевой тип.  
  
 `pbHashValue`  
 [in] Массив, содержащий хэш-код для сборки, определяемой параметром `pAssemImport`.  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 [in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс, представляющий область метаданных, из которого импортируется в целевой тип.  
  
 `tdImport`  
 [in] `mdTypeDef` Маркер, который указывает тип целевого объекта.  
  
 `pAssemEmit`  
 [in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) интерфейс, представляющий сборку, в который импортируется в целевой тип.  
  
 `ptr`  
 [out] `mdTypeRef` Маркер, который определен в текущей области для ссылки на тип.  
  
## <a name="remarks"></a>Примечания  
 До вызова метода [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) метод, можно использовать `DefineImportType` метод, чтобы создать ссылку на тип, в текущей области для родительского класса или интерфейса родительского элемента.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
