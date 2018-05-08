---
title: Метод IMetaDataAssemblyEmit::DefineExportedType
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2eb894a8bac702c30826d1e965c91cae9b259ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>Метод IMetaDataAssemblyEmit::DefineExportedType
Создает структуру `ExportedType`, содержащую метаданные для указанного экспортированного типа, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szName`  
 [in] Имя типа должны быть экспортированы. Версии 1.1 среды common language runtime имя экспортируемого типа должно точно соответствовать имени в `TypeDef` для типа.  
  
 `tkImplementation`  
 [in] Токен, указав, где реализуется экспортируемого типа. Ниже приведены допустимые значения и их связанные значения.  
  
-   `mdFile` Тип реализуется в другой файл в этой сборке.  
  
-   `mdAssemblyRef` Тип реализуется в другой сборке.  
  
-   `mdExportedTYpe` Тип, вложенный в другой тип.  
  
-   `mdFileNil` Тип находится в тот же файл манифеста и не является вложенным типом.  
  
 `tkTypeDef`  
 [in] Токен метаданных, указывающий тип для экспорта. Это значение, введенное в `TypeDef` таблице в файле, который реализует тип элемента и используется только в том случае, если этот файл находится в этой сборке.  
  
 `dwExportedTypeFlags`  
 [in] Побитовое сочетание [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) значений перечисления, определяющих параметры свойств для экспортируемого типа.  
  
 `pmdct`  
 [out] Указатель на токен возвращенные метаданные, указывающее экспортируемого типа.  
  
## <a name="remarks"></a>Примечания  
 `ExportedType` Структуру метаданных должны быть определены для каждого типа, представленного этой сборке и реализуемую в модуле, отличном от того, содержащем манифест.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
