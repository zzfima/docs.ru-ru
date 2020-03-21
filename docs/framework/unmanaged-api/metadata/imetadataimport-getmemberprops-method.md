---
title: Метод IMetaDataImport::GetMemberProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177232"
---
# <a name="imetadataimportgetmemberprops-method"></a>Метод IMetaDataImport::GetMemberProps
Получает информацию, хранящуюся в метаданных для определенного определения участника, <xref:System.Type> включая имя, двоичную подпись и относительный виртуальный адрес, участника, на которого ссылается указанный маркер метаданных. Это простой метод помощника: если *mb* является MethodDef, то **GetMethodProps** называется; если *mb* является FieldDef, то **GetFieldProps** называется. Ознакомьтесь с другими методами для получения подробной информации.
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mb`  
 (в) Токен, который ссылается на символ для получения связанных метаданных.  
  
 `pClass`  
 (ваут) Указатель на маркер метаданных, представляющий класс участника.  
  
 `szMember`  
 (ваут) Имя участника.  
  
 `cchMember`  
 (в) Размер в широких символах буфера. `szMember`  
  
 `pchMember`  
 (ваут) Размер в широких символах возвращенного имени.  
  
 `pdwAttr`  
 (ваут) Любые значения флага, применяемые к участнику.  
  
 `ppvSigBlob`  
 (ваут) Указатель на двоичную подпись метаданных участника.  
  
 `pcbSigBlob`  
 (ваут) Размер байтов `ppvSigBlob`.  
  
 `pulCodeRVA`  
 (ваут) Указатель на относительный виртуальный адрес участника.  
  
 `pdwImplFlags`  
 (ваут) Флаги реализации любого метода, связанные с участником.  
  
 `pdwCPlusTypeFlag`  
 (ваут) Флаг, который <xref:System.ValueType>отмечает . Это одна из `ELEMENT_TYPE_*` ценностей.
  
 `ppValue`  
 (ваут) Постоянное значение строки, возвращенное этим участником.  
  
 `pcchValue`  
 (ваут) Размер в `ppValue`символах, или `ppValue` ноль, если не держит строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
