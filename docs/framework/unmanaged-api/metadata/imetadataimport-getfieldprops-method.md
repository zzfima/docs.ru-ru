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
ms.openlocfilehash: 462512fd2c2b33905b45bb67599b23b301fc71f7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437992"
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
 окне Токен FieldDef, представляющий поле, для которого нужно получить связанные метаданные.  
  
 `pClass`  
 заполняет Указатель на маркер TypeDef, представляющий тип класса, которому принадлежит поле.  
  
 `szField`  
 заполняет Имя поля.  
  
 `cchField`  
 окне Размер в расширенных символах буфера для *сзфиелд*.  
  
 `pchField`  
 заполняет Фактический размер возвращаемого буфера.  
  
 `pdwAttr`  
 заполняет Флаги, связанные с метаданными поля.  
  
 `ppvSigBlob`  
 окне Указатель на двоичное значение метаданных, описывающее поле.  
  
 `pcbSigBlob`  
 заполняет Размер в байтах `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 заполняет Флаг, указывающий тип значения поля.  
  
 `ppValue`  
 заполняет Постоянное значение для поля.  
  
 `pcchValue`  
 заполняет Размер в символах `ppValue`или нуль, если строка не существует.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
