---
title: Метод IMetaDataImport::EnumMemberRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34a6762618780b22bcd8be376209912390524578
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592024"
---
# <a name="imetadataimportenummemberrefs-method"></a>Метод IMetaDataImport::EnumMemberRefs
Перечисляет токены MemberRef, представляющие члены указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель.  
  
 `tkParent`  
 [in] Токен TypeDef, TypeRef, MethodDef или ModuleRef, представляющий тип, члены которого необходимо перечислить.  
  
 `rMemberRefs`  
 [out] Массив, используемый для хранения токены MemberRef.  
  
 `cMax`  
 [in] Максимальный размер массива `rMemberRefs`.  
  
 `pcTokens`  
 [out] Фактическое число токены MemberRef, возвращаемых в `rMemberRefs`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры MemberRef для перечисления отсутствуют. В этом случае `pcTokens` имеет значение нуль.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
