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
ms.openlocfilehash: 04b6c04868efff31253b2d723c5783060382212b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448977"
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
  
#### <a name="parameters"></a>Параметры  
 `mb`  
 [in] Представляющий поле, чтобы получить связанные метаданные для токен FieldDef.  
  
 `pClass`  
 [out] Указатель на токен TypeDef, представляющий тип класса, к которому принадлежит поле.  
  
 `szField`  
 [out] Имя поля.  
  
 `cchField`  
 [in] Размер в расширенных символах, буфера для *szField*.  
  
 `pchField`  
 [out] Фактический размер возвращенного буфера.  
  
 `pdwAttr`  
 [out] Флаги, связанные с поля метаданных.  
  
 `ppvSigBlob`  
 [in] Указатель на значение двоичного метаданных с описанием поля.  
  
 `pcbSigBlob`  
 [out] Размер в байтах `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Флаг, указывающий тип значения поля.  
  
 `ppValue`  
 [out] Постоянное значение для поля.  
  
 `pcchValue`  
 [out] Размер в символах для `ppValue`, или нуль, если строка не существует.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
