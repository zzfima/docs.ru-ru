---
title: Метод IMetaDataEmit::DefineProperty
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175789"
---
# <a name="imetadataemitdefineproperty-method"></a>Метод IMetaDataEmit::DefineProperty
Создает определение свойства для указанного типа `get` `set` с указанными и доступными для метода, и получает маркер к определению этого свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 (в) Токен для класса или интерфейса, на котором определяется свойство.  
  
 `szProperty`  
 [in] Имя свойства.  
  
 `dwPropFlags`  
 (в) Флаги свойств.  
  
 `pvSig`  
 (в) Подпись собственности.  
  
 `cbSig`  
 (в) Количество байтов `pvSig`в .  
  
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
 (в) Массив других методов, связанных с свойством. Упраздните `mdTokenNil`массив с помощью .  
  
 `pmdProp`  
 (ваут) Назначенный `mdProperty` маркер.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
