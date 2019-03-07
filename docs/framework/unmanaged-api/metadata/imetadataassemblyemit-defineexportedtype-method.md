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
ms.openlocfilehash: 984eef16ff576d63a445b199eba8c2364285f62e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483878"
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
  
## <a name="parameters"></a>Параметры  
 `szName`  
 [in] Имя типа должны быть экспортированы. Для версии 1.1 среда CLR, имя экспортируемого типа должен точно соответствовать имени, заданному в `TypeDef` для типа.  
  
 `tkImplementation`  
 [in] Токен, указав, где реализуется экспортированный тип. Ниже приведены допустимые значения и их связанные значения.  
  
-   `mdFile` Тип реализуется в другой файл в этой сборке.  
  
-   `mdAssemblyRef` Тип реализуется в другой сборке.  
  
-   `mdExportedTYpe` Тип является вложенным в другой тип.  
  
-   `mdFileNil` Тип находится в тот же файл манифеста и не является вложенным типом.  
  
 `tkTypeDef`  
 [in] Токен метаданных, указывающий тип для экспорта. Это значение вводится в `TypeDef` таблицы в файл, который реализует тип элемента и используется только в том случае, если этот файл находится в этой сборке.  
  
 `dwExportedTypeFlags`  
 [in] Побитовое сочетание [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) значений перечисления, определяющих значения свойств для экспортируемого типа.  
  
 `pmdct`  
 [out] Указатель на токен метаданных, возвращаемых, указывающее экспортированный тип.  
  
## <a name="remarks"></a>Примечания  
 `ExportedType` Структура метаданных должны быть определены для каждого типа, представленного этой сборки и который реализуется в модуле, отличном от того, содержащем манифест.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
