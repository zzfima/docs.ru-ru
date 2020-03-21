---
title: Метод IMetaDataEmit::DefineNestedType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175815"
---
# <a name="imetadataemitdefinenestedtype-method"></a>Метод IMetaDataEmit::DefineNestedType
Создает подпись метаданных определения типа, `mdTypeDef` возвращает маркер для этого типа и указывает, что определенный тип является членом типа, на который ссылается `tdEncloser` параметр.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szTypeDef`  
 (в) Название типа в Unicode.  
  
 `dwTypeDefFlags`  
 (в) `TypeDef` атрибуты. Это битмаска ценностей. `CorTypeAttr`  
  
 `tkExtends`  
 (в) Токен базового класса. Это либо `mdTypeDef` знак, `mdTypeRef` либо жетон.  
  
 `rtkImplements`[]  
 (в) Массив токенов, определяющих интерфейсы, реализуемые этим классом или интерфейсом.  
  
 `tdEncloser`  
 (в) Токен типа прилагаемого. Последний элемент массива `mdTokenNil`должен быть.  
  
 `ptd`  
 (ваут) Назначенный `mdTypeDef` маркер.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
