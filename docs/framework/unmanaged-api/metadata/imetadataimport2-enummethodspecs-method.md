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
ms.openlocfilehash: a3641fcda33a497293dbf87b419c8606847dc296
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130953"
---
# <a name="imetadataimport2enummethodspecs-method"></a>Метод IMetaDataImport2::EnumMethodSpecs
Получает перечислитель для массива MethodSpec токенов, связанных с указанным MethodDef или MemberRef маркер.  
  
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
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель для `rMethodSpecs`.  
  
 `tk`  
 [in] Токен MemberRef или MethodDef, представляющий метод, маркеры которого MethodSpec будут перечислены. Если значение `tk` равно 0 (ноль), будут перечислены все маркеры MethodSpec в области.  
  
 `rMethodSpecs`  
 [out] Массив MethodSpec маркеры для перечисления.  
  
 `cMax`  
 [in] Максимальное число маркеров для размещения в `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 [out] Возвращенное число маркеров помещаются в `rMethodSpecs`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs` успешно возвращен.|  
|`S_FALSE`|`phEnum` не имеет члена элементов. В этом случае `pcMethodSpecs` имеет значение 0 (ноль).|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
