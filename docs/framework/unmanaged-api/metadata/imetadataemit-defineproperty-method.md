---
title: "Метод IMetaDataEmit::DefineProperty"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: accc6503cc9fb87d39a429331dc82ff5717f6989
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineproperty-method"></a>Метод IMetaDataEmit::DefineProperty
Создает определение свойства для указанного типа с указанным `get` и `set` метод доступа и получает маркер для этого определения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] Токен для класса или интерфейса, на котором определено свойство.  
  
 `szProperty`  
 [in] Имя свойства.  
  
 `dwPropFlags`  
 [in] Флаги свойства.  
  
 `pvSig`  
 [in] Сигнатура свойства.  
  
 `cbSig`  
 [in] Число байт в `pvSig`.  
  
 `dwCPlusTypeFlag`  
 [in] Тип значения по умолчанию этого свойства.  
  
 `pValue`  
 [in] Значение по умолчанию для свойства.  
  
 `cchValue`  
 [in] Количество (Юникод) символы в `pValue`.  
  
 `mdSetter`  
 [in] Метод, который задает значение свойства.  
  
 `mdGetter`  
 [in] Метод, который возвращает значение свойства.  
  
 `rmdOtherMethods[]`  
 [in] Массив из других методов, связанное со свойством. Массива с `mdTokenNil`.  
  
 `pmdProp`  
 [out] `mdProperty` Маркер, назначенный.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
