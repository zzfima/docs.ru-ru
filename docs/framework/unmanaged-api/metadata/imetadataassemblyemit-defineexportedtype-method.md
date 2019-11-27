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
ms.openlocfilehash: 44f97ef498eb8e64c55fc86b9f290b9e088293f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432066"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>Метод IMetaDataAssemblyEmit::DefineExportedType
Создает структуру `ExportedType`, содержащую метаданные для указанного экспортированного типа, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 окне Имя экспортируемого типа. Для версии 1,1 среды CLR имя экспортируемого типа должно точно совпадать с именем, заданным в `TypeDef` для типа.  
  
 `tkImplementation`  
 окне Токен, указывающий, где реализуется экспортируемый тип. Допустимые значения и их связанное с ними значение:  
  
- `mdFile` тип реализуется в другом файле в этой сборке.  
  
- `mdAssemblyRef` тип реализован в другой сборке.  
  
- `mdExportedTYpe` тип вложен в другой тип.  
  
- `mdFileNil` тип находится в том же файле, что и манифест, и не является вложенным типом.  
  
 `tkTypeDef`  
 окне Токен метаданных, указывающий тип для экспорта. Это значение вводится в таблицу `TypeDef` в файле, который реализует тип, и имеет смысл только в том случае, если этот файл находится в этой сборке.  
  
 `dwExportedTypeFlags`  
 окне Побитовое сочетание значений перечисления [кортипеаттр](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) , определяющих настройки свойств для экспортируемого типа.  
  
 `pmdct`  
 заполняет Указатель на возвращаемый маркер метаданных, указывающий на экспортируемый тип.  
  
## <a name="remarks"></a>Заметки  
 Структура метаданных `ExportedType` должна быть определена для каждого типа, предоставляемого этой сборкой и реализованного в модуле, отличном от того, который содержит манифест.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
