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
ms.openlocfilehash: 8c3f98a124dbbcae3b0500932a2357ed1757951f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177238"
---
# <a name="imetadataimportgetfieldprops-method"></a>Метод IMetaDataImport::GetFieldProps
Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 (в) Токен FieldDef, представляющий поле для получения связанных метаданных.  
  
 `pClass`  
 (ваут) Указатель на маркер TypeDef, представляющий тип класса, к которому принадлежит поле.  
  
 `szField`  
 (ваут) Название поля.  
  
 `cchField`  
 (в) Размер в широких символах буфера для *szField*.  
  
 `pchField`  
 (ваут) Фактический размер возвращенного буфера.  
  
 `pdwAttr`  
 (ваут) Флаги, связанные с метаданными поля.  
  
 `ppvSigBlob`  
 (в) Указатель на двоичное значение метаданных, описывающий поле.  
  
 `pcbSigBlob`  
 (ваут) Размер байтов `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 (ваут) Флаг, описавательный тип значения поля.  
  
 `ppValue`  
 (ваут) Постоянное значение для поля.  
  
 `pcchValue`  
 (ваут) Размер в символах, или ноль, если строка `ppValue`не существует.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
