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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7676c83e8b231606896cb6d1224633b4fa15e725
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777568"
---
# <a name="imetadataemitdefinenestedtype-method"></a>Метод IMetaDataEmit::DefineNestedType
Создает подпись метаданных определения типа, возвращает `mdTypeDef` маркеров для этого типа и указывает, что определенный тип является членом типа, который ссылается `tdEncloser` параметра.  
  
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
 [in] Имя типа в формате Юникод.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` атрибуты. Это битовая маска `CorTypeAttr` значения.  
  
 `tkExtends`  
 [in] Токен базового класса. Это может быть либо `mdTypeDef` или `mdTypeRef` токена.  
  
 `rtkImplements`[]  
 [in] Массив токенов, которые указывают интерфейсы, реализуемые этот класс или интерфейс.  
  
 `tdEncloser`  
 [in] Токен данного включающего типа. Последний элемент массива должен быть `mdTokenNil`.  
  
 `ptd`  
 [out] `mdTypeDef` Маркер, назначенный.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
