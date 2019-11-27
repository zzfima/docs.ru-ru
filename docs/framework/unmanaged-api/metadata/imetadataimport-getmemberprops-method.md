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
ms.openlocfilehash: bc5bbba2fa4a95955e52a2e083a2097178b5d96a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437518"
---
# <a name="imetadataimportgetmemberprops-method"></a>Метод IMetaDataImport::GetMemberProps
Возвращает сведения, хранящиеся в метаданных для указанного определения элемента, включая имя, двоичную подпись и относительный виртуальный адрес элемента <xref:System.Type>, на который ссылается указанный маркер метаданных. Это простой вспомогательный метод: Если *МБ* является MethodDef, то вызывается **жетмесодпропс** . Если *МБ* является FieldDef, вызывается **жетфиелдпропс** . Дополнительные сведения см. в этих других методах. 
  
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
 окне Токен, ссылающийся на элемент, для которого необходимо получить связанные метаданные.  
  
 `pClass`  
 заполняет Указатель на маркер метаданных, представляющий класс члена.  
  
 `szMember`  
 заполняет Имя элемента.  
  
 `cchMember`  
 окне Размер в расширенных символах буфера `szMember`.  
  
 `pchMember`  
 заполняет Размер в расширенных символах возвращаемого имени.  
  
 `pdwAttr`  
 заполняет Все значения флагов, примененные к элементу.  
  
 `ppvSigBlob`  
 заполняет Указатель на сигнатуру двоичных метаданных элемента.  
  
 `pcbSigBlob`  
 заполняет Размер в байтах `ppvSigBlob`.  
  
 `pulCodeRVA`  
 заполняет Указатель на относительный виртуальный адрес элемента.  
  
 `pdwImplFlags`  
 заполняет Любые флаги реализации метода, связанные с элементом.  
  
 `pdwCPlusTypeFlag`  
 заполняет Флаг, помечающий <xref:System.ValueType>. Это одно из значений `ELEMENT_TYPE_*`.
  
 `ppValue`  
 заполняет Константное строковое значение, возвращаемое этим элементом.  
  
 `pcchValue`  
 заполняет Размер в символах `ppValue`или нуль, если `ppValue` не содержит строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
