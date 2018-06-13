---
title: Метод IMetaDataImport::GetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa69eda974187748d7046c792fa16b7729e3deff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446886"
---
# <a name="imetadataimportgettypedefprops-method"></a>Метод IMetaDataImport::GetTypeDefProps
Возвращает сведения о метаданных для <xref:System.Type> представленного указанным токеном TypeDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] Представляющий тип, для возврата метаданных для токен TypeDef.  
  
 `szTypeDef`  
 [out] Буфер, содержащий имя типа.  
  
 `cchTypeDef`  
 [in] Размер в расширенных символах с `szTypeDef`.  
  
 `pchTypeDef`  
 [out] Число расширенных символов, возвращаемых в `szTypeDef`.  
  
 `pdwTypeDefFlags`  
 [out] Указатель на любой флаги, которые изменяют определения типа. Это значение является битовой [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) перечисления.  
  
 `ptkExtends`  
 [out] TypeDef или TypeRef токен метаданных, представляющий базовый тип запрошенного типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
