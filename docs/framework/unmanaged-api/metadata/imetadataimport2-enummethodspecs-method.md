---
title: Метод IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c2122c06c6e4f1137173f02e37fb0982864e7ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimport2enummethodspecs-method"></a>Метод IMetaDataImport2::EnumMethodSpecs
Возвращает перечислитель для массива маркеров MethodSpec, связанных с указанным MethodDef или MemberRef токен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель для `rMethodSpecs`.  
  
 `tk`  
 [in] Токен MemberRef или MethodDef, представляющий метод, маркеры которого MethodSpec для перечисления. Если значение `tk` равно 0 (ноль), будут перечислены все маркеры MethodSpec в области.  
  
 `rMethodSpecs`  
 [out] Массив MethodSpec маркеры для перечисления.  
  
 `cMax`  
 [in] Максимальное количество маркеров для размещения в `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 [out] Возвращенное число маркеров помещаются в `rMethodSpecs`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` успешно возвращен.|  
|`S_FALSE`|`phEnum` не имеет члена элементов. В этом случае `pcMethodSpecs` имеет значение 0 (ноль).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
