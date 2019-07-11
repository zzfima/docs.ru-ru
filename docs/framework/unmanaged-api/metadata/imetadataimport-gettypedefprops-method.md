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
ms.openlocfilehash: 77f72fb7eb7b0542dc9a3179811a78b189d6b3b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778838"
---
# <a name="imetadataimportgettypedefprops-method"></a>Метод IMetaDataImport::GetTypeDefProps
Возвращает сведения о метаданных для <xref:System.Type> представленного указанным токеном TypeDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 [in] Токен TypeDef, который представляет метаданные для возвращаемого типа.  
  
 `szTypeDef`  
 [out] Буфер, содержащий имя типа.  
  
 `cchTypeDef`  
 [in] Размер в расширенных символах `szTypeDef`.  
  
 `pchTypeDef`  
 [out] Число расширенных символов, возвращаемых в `szTypeDef`.  
  
 `pdwTypeDefFlags`  
 [out] Указатель на всех флагов изменить определение типа. Это значение является битовой [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) перечисления.  
  
 `ptkExtends`  
 [out] Определение типа или TypeRef токен метаданных, представляющий базовый тип запрошенного типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
