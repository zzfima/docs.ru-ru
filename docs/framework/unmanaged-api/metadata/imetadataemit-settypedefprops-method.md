---
title: Метод IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447718"
---
# <a name="imetadataemitsettypedefprops-method"></a>Метод IMetaDataEmit::SetTypeDefProps
Задает функции типа, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинетипедеф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 окне Маркер `mdTypeDef`, полученный из исходного вызова функции [IMetaDataEmit::D ефинетипедеф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` атрибуты. Это битовая маска `CorTypeAttr` значений.  
  
 `tkExtends`  
 окне `mdToken` базового класса. Получено из предыдущего вызова [IMetaDataEmit::D ефинеимпорттипе](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)или `null`.  
  
 `rtkImplements[]`  
 окне Массив токенов для интерфейсов, реализуемых этим типом. Эти `mdTypeRef` токены получаются с помощью метода [IMetaDataEmit::D ефинеимпорттипе](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md). Последний элемент массива должен быть `mdTokenNil`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
