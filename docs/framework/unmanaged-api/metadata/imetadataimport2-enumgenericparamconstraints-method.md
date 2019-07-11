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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ba9d7f8873d15a7cab2b9893feb8563dfc971b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778759"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a>Метод IMetaDataImport2::EnumGenericParamConstraints
Получает перечислитель для массива универсальный параметр ограничения, связанные с универсального параметра, представленного указанным токеном.  
  
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
 [in, out] Указатель на перечислитель.  
  
 `tk`  
 [in]   Токен, который представляет универсальный параметр, ограничения должны быть перечислены.  
  
 `rGenericParamConstraints`  
 [out] Массив ограничений параметра универсального типа для перечисления.  
  
 `cMax`  
 [in]   Максимальное число маркеров для размещения в `rGenericParamConstraints`.  
  
 `pcGenericParamConstraints`  
 [out] Указатель на число маркеров помещаются в `rGenericParamConstraints`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParameterConstraints` успешно возвращен.|  
|`S_FALSE`|`phEnum` не имеет члена элементов. В этом случае `pcGenericParameterConstraints` имеет значение 0 (ноль).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
