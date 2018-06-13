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
ms.openlocfilehash: 0d62b9be1bef16014e2870c15a232bb46d4daf10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448756"
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
  
#### <a name="parameters"></a>Параметры  
 `mr`  
 [in] Токен MemberRef для возврата связанные с ним метаданные.  
  
 `ptk`  
 [out] Токен TypeDef или TypeRef или TypeSpec, представляющий класс, который объявляет член, или токен ModuleRef, представляющий класс модуля, который объявляет член или MethodDef, который представляет элемент.  
  
 `szMember`  
 [out] Строковый буфер для имени элемента.  
  
 `cchMember`  
 [in] Запрошенный размер в расширенных символах с `szMember`.  
  
 `pchMember`  
 [out] Возвращаемый размер в расширенных символах с `szMember`.  
  
 `ppvSibBlob`  
 [out] Указатель на двоичную подпись метаданных для элемента.  
  
 `pbSig`  
 [out] Размер в байтах `ppvSigBlob`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
