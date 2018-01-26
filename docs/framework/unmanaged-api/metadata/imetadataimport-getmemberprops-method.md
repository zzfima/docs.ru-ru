---
title: "Метод IMetaDataImport::GetMemberProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 543929390977fc593e86947feece06f43bc0cad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmemberprops-method"></a>Метод IMetaDataImport::GetMemberProps
Возвращает сведения о метаданных, в том числе имя, двоичную подпись и относительный виртуальный адрес из <xref:System.Type> члена ссылается указанный токен метаданных.  
  
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
 [out] Указатель на токен метаданных, представляющий класс элемента.  
  
 `szMember`  
 [out] Имя элемента.  
  
 `cchMember`  
 [in] Размер в расширенных символах с `szMember` буфера.  
  
 `pchMember`  
 [out] Размер в расширенных символах возвращаемое имя.  
  
 `pdwAttr`  
 [out] Любые значения флага, применении к элементу.  
  
 `ppvSigBlob`  
 [out] Указатель на двоичную подпись метаданных элемента.  
  
 `pcbSigBlob`  
 [out] Размер в байтах `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Указатель на относительный виртуальный адрес элемента.  
  
 `pdwImplFlags`  
 [out] Любые флаги реализации метода, связанное с элементом.  
  
 `pdwCPlusTypeFlag`  
 [out] Флаг, обозначающий <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Постоянное строковое значение, возвращенное этим членом.  
  
 `pcchValue`  
 [out] Размер в символах `ppValue`, или нуль, если `ppValue` не содержит строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
