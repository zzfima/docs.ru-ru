---
title: Метод IMetaDataImport::GetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7f8cccf8d583645982eb37f6afcb553914679ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075679"
---
# <a name="imetadataimportgetfieldprops-method"></a>Метод IMetaDataImport::GetFieldProps
Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mb`  
 [in] Токен FieldDef, который представляет связанные метаданные для поля.  
  
 `pClass`  
 [out] Указатель на токен TypeDef, представляющий тип класса, которой принадлежит это поле.  
  
 `szField`  
 [out] Имя поля.  
  
 `cchField`  
 [in] Размер в расширенных символах, буфера для *szField*.  
  
 `pchField`  
 [out] Фактический размер возвращенного буфера.  
  
 `pdwAttr`  
 [out] Флаги, связанные с метаданными поля.  
  
 `ppvSigBlob`  
 [in] Указатель на значение двоичных метаданных, описывающий поле.  
  
 `pcbSigBlob`  
 [out] Размер в байтах `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Флаг, указывающий тип значения поля.  
  
 `ppValue`  
 [out] Постоянное значение для поля.  
  
 `pcchValue`  
 [out] Размер в символы `ppValue`, или нуль, если строка не существует.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
