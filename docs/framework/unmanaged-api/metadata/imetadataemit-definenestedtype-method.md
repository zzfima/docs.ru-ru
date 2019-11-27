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
ms.openlocfilehash: 5d985e22ba77053127610445374b8c13ca6b97f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431702"
---
# <a name="imetadataemitdefinenestedtype-method"></a>Метод IMetaDataEmit::DefineNestedType
Создает сигнатуру метаданных определения типа, возвращает маркер `mdTypeDef` для этого типа и указывает, что определенный тип является членом типа, на который ссылается параметр `tdEncloser`.  
  
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
 окне Имя типа в Юникоде.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` атрибуты. Это битовая маска `CorTypeAttr` значений.  
  
 `tkExtends`  
 окне Маркер базового класса. Это либо `mdTypeDef`, либо маркер `mdTypeRef`.  
  
 `rtkImplements`[]  
 окне Массив токенов, задающих интерфейсы, реализуемые этим классом или интерфейсом.  
  
 `tdEncloser`  
 окне Токен включающего типа. Последний элемент массива должен быть `mdTokenNil`.  
  
 `ptd`  
 заполняет Назначенный маркер `mdTypeDef`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
