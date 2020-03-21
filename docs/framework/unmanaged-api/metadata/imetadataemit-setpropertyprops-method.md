---
title: Метод IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: dc6375f3e2cff1a744a8ff2e6a6adab27bbf8af3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177476"
---
# <a name="imetadataemitsetpropertyprops-method"></a>Метод IMetaDataEmit::SetPropertyProps
Устанавливает функции, хранящиеся в метаданных, для свойства, определяемого предыдущим вызовом [методу DefineProperty.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pr`  
 (в) Токен для изменения свойства  
  
 `dwPropFlags`  
 (в) Флаги свойств.  
  
 `dwCPlusTypeFlag`  
 (в) Тип значения по умолчанию.  
  
 `pValue`  
 (в) Значение значения по умолчанию для свойства.  
  
 `cchValue`  
 (в) Количество символов (Unicode) `pValue`в .  
  
 `mdSetter`  
 (в) Метод, устанавливающие значение свойства.  
  
 `mdGetter`  
 (в) Метод, который получает значение свойства.  
  
 `rmdOtherMethods[]`  
 (в) Массив других методов, связанных с свойством. Прекратите этот `mdTokenNil` массив с помощью маркера.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
