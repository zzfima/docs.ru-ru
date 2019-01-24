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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98d7be5adc81cff09b121265e7d5b5f712122607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611414"
---
# <a name="imetadataimportgetmemberprops-method"></a>Метод IMetaDataImport::GetMemberProps
Возвращает сведения о метаданных, в том числе имя, двоичную подпись и относительный виртуальный адрес <xref:System.Type> члена ссылается указанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `mb`  
 [in] Токен, который ссылается на связанные метаданные для члена.  
  
 `pClass`  
 [out] Указатель на токен метаданных, представляющий класс члена.  
  
 `szMember`  
 [out] Имя элемента.  
  
 `cchMember`  
 [in] Размер в расширенных символах `szMember` буфера.  
  
 `pchMember`  
 [out] Размер в расширенных символах возвращаемое имя.  
  
 `pdwAttr`  
 [out] Любые значения флага, применения к элементу.  
  
 `ppvSigBlob`  
 [out] Указатель на двоичную подпись метаданных элемента.  
  
 `pcbSigBlob`  
 [out] Размер в байтах `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Указатель на относительный виртуальный адрес элемента.  
  
 `pdwImplFlags`  
 [out] Все флаги реализации метода, связанное с элементом.  
  
 `pdwCPlusTypeFlag`  
 [out] Флаг, который помечает <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Постоянное строковое значение, возвращаемое этим элементом.  
  
 `pcchValue`  
 [out] Размер в символах `ppValue`, или нуль, если `ppValue` не содержит строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
