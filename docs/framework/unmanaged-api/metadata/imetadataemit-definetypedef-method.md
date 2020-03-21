---
title: Метод IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175763"
---
# <a name="imetadataemitdefinetypedef-method"></a>Метод IMetaDataEmit::DefineTypeDef
Создает определение типа для общего типа времени выполнения языка и получает токен метаданных для определения этого типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szTypeDef`  
 (в) Название типа в Unicode.  
  
 `dwTypeDefFlags`  
 (в) `TypeDef` атрибуты. Это битмаска ценностей. `CoreTypeAttr`  
  
 `tkExtends`  
 (в) Токен базового класса. Это должен быть `mdTypeDef` либо `mdTypeRef` знак, либо жетон.  
  
 `rtkImplements`  
 (в) Массив токенов, указывающих интерфейсы, которые реализует этот класс или интерфейс.  
  
 `ptd`  
 (ваут) Назначенный `mdTypeDef` маркер.  
  
## <a name="remarks"></a>Remarks  
 Флаг в `dwTypeDefFlags` опознавательных данных определяет, является ли создаваемый тип обычным типом системы (класс или интерфейс) или общим типом значения системы.  
  
 В зависимости от поставленных параметров, этот метод, как `mdInterfaceImpl` побочный эффект, может также создать запись для каждого интерфейса, который наследуется или реализован этим типом. Однако этот метод не возвращает `mdInterfaceImpl` ни одного из этих токенов. Если клиент хочет позже добавить или изменить `mdInterfaceImpl` маркер, он должен использовать `IMetaDataImport` интерфейс для их перечисления. Если вы хотите использовать семантику интерфейса `[default]` COM, следует предоставить `rtkImplements`интерфейс по умолчанию в качестве первого элемента в; пользовательский набор атрибутов в классе будет указывать на то, что класс `mdInterfaceImpl` имеет интерфейс по умолчанию (который всегда считается первым маркером, объявленным для класса).  
  
 Каждый элемент `rtkImplements` массива `mdTypeDef` `mdTypeRef` содержит маркер или жетон. Последний элемент в массиве должен быть. `mdTokenNil`  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
