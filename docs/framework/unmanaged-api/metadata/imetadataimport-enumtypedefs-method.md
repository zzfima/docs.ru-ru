---
title: Метод IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53ed486a885514d02bf2be9c473e102c2c5f0e15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenumtypedefs-method"></a>Метод IMetaDataImport::EnumTypeDefs
Перечисляет токены TypeDef, представляющие все типы в текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [out] Указатель на новый перечислитель. Это должно быть NULL при первом вызове этого метода.  
  
 `rTypeDefs`  
 [in] Массив, используемый для хранения токенов TypeDef.  
  
 `cMax`  
 [in] Максимальный размер массива `rTypeDefs`.  
  
 `pcTypeDefs`  
 [out] Число токены TypeDef, возвращаемых в `rTypeDefs`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры для перечисления отсутствуют. В этом случае `pcTypeDefs` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Маркер TypeDef представляет тип, например класс или интерфейс, а также любой тип, добавленный посредством механизма расширяемости.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
