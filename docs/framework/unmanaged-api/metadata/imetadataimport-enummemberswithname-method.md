---
title: Метод IMetaDataImport::EnumMembersWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fca698adc4d08d805fec2ff80af377366674b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenummemberswithname-method"></a>Метод IMetaDataImport::EnumMembersWithName
Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель.  
  
 `cl`  
 [in] Токен TypeDef, представляющий тип с члены для перечисления.  
  
 `szName`  
 [in] Имя члена, который ограничивает область перечислителя.  
  
 `rMembers`  
 [out] Массив, используемый для хранения MemberDef токенов.  
  
 `cMax`  
 [in] Максимальный размер массива `rMembers`.  
  
 `pcTokens`  
 [out] Фактическое число токены MemberDef, возвращаемых в `rMembers`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод перечисляет поля и методы, но не свойств или событий. В отличие от [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` отменяет все маркеры полей и элементов, которые имеют указанное имя.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры MemberDef для перечисления отсутствуют. В этом случае `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
