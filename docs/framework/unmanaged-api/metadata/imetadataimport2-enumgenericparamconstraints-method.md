---
title: Метод IMetaDataImport2::EnumGenericParamConstraints
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
ms.openlocfilehash: d1683965193801dbdee038ab06366178891fd978
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426722"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a>Метод IMetaDataImport2::EnumGenericParamConstraints
Возвращает перечислитель для массива ограничений универсальных параметров, связанных с универсальным параметром, представленным указанным токеном.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `tk`  
 окне   Токен, представляющий универсальный параметр, ограничения которого необходимо перечислить.  
  
 `rGenericParamConstraints`  
 заполняет Массив ограничений универсального параметра для перечисления.  
  
 `cMax`  
 окне   Запрошенное максимальное число токенов, помещаемых в `rGenericParamConstraints`.  
  
 `pcGenericParamConstraints`  
 заполняет Указатель на число токенов, помещенных в `rGenericParamConstraints`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` успешно возвращено.|  
|`S_FALSE`|у `phEnum` нет элементов Member. В этом случае `pcGenericParameterConstraints` имеет значение 0 (ноль).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
