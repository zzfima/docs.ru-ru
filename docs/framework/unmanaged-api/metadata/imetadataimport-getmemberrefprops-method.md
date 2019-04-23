---
title: Метод IMetaDataImport::GetMemberRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2c431abb7a4a872454b9c2689ee195ed36ef236
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177018"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>Метод IMetaDataImport::GetMemberRefProps
Возвращает метаданные, связанные с членом, на который ссылается указанный токен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mr`  
 [in] Токен MemberRef для возврата связанные метаданные для.  
  
 `ptk`  
 [out] Токен TypeDef или TypeRef или TypeSpec, который представляет класс, который объявляет член, или токен ModuleRef, представляющий класс модуля, который объявляет член, или MethodDef, представляемого члена.  
  
 `szMember`  
 [out] Строковый буфер для имени члена.  
  
 `cchMember`  
 [in] Запрошенный размер в расширенных символах `szMember`.  
  
 `pchMember`  
 [out] Возвращаемый размер в расширенных символах `szMember`.  
  
 `ppvSibBlob`  
 [out] Указатель на двоичную подпись метаданных для элемента.  
  
 `pbSig`  
 [out] Размер в байтах `ppvSigBlob`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
