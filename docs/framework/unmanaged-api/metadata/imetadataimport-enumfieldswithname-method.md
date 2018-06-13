---
title: Метод IMetaDataImport::EnumFieldsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6ed8bbbd9699fe707d638bb8d07064e508b6f2fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447776"
---
# <a name="imetadataimportenumfieldswithname-method"></a>Метод IMetaDataImport::EnumFieldsWithName
Перечисляет токены FieldDef заданного типа с указанным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель.  
  
 `cl`  
 [in] Токен типа, поля которого предназначены для перечисления.  
  
 `szName`  
 [in] Имя поля, которое ограничивает область перечисления.  
  
 `rFields`  
 [out] Массив, используемый для хранения токены FieldDef.  
  
 `cMax`  
 [in] Максимальный размер массива `rFields`.  
  
 `pcTokens`  
 [out] Фактическое число возвращенных в токены FieldDef `rFields`.  
  
## <a name="remarks"></a>Примечания  
 В отличие от [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` отменяет все маркеры поля, которые имеют указанное имя.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumFieldsWithName` успешно возвращен.|  
|`S_FALSE`|Нет полей для перечисления. В этом случае `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
