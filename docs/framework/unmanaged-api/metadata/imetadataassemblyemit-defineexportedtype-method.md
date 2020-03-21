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
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177881"
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
 (в) Название типа, которое будет экспортироваться. Для версии 1.1 общего времени выполнения языка имя экспортируемого типа должно `TypeDef` точно соответствовать названию, приведенному в типе.  
  
 `tkImplementation`  
 (в) Токен с указанием места реализации экспортируемого типа. Действительные значения и связанные с ними значения:  
  
- `mdFile`Тип реализован в другом файле в этой сборке.  
  
- `mdAssemblyRef`Тип реализован в другой сборке.  
  
- `mdExportedTYpe`Тип вложен в какой-либо другой тип.  
  
- `mdFileNil`Тип находится в том же файле, что и манифест, и не является вложенным типом.  
  
 `tkTypeDef`  
 (в) Токен к метаданным, который определяет тип, который будет экспортироваться. Это значение вводится `TypeDef` в таблицу в файле, который реализует тип и актуален только в том случае, если этот файл находится в этой сборке.  
  
 `dwExportedTypeFlags`  
 (в) Битовая комбинация значений [corTypeAttr,](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) определяющих параметры свойств для экспортируемого типа.  
  
 `pmdct`  
 (ваут) Указатель на токен возвращенных метаданных, указывающий на экспортированный тип.  
  
## <a name="remarks"></a>Remarks  
 Структура `ExportedType` метаданных должна быть определена для каждого типа, который подвергается этой сборке и реализован в модуле, кроме того, который содержит манифест.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
