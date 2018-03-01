---
title: "Метод IMetaDataImport::GetMethodProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e0ae7dfed4b13ea83e16d6380443c9d1b72b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodprops-method"></a>Метод IMetaDataImport::GetMethodProps
Возвращает метаданные, связанные с методом, на который ссылается указанный токен MethodDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mb`  
 [in] Токен MethodDef, который представляет метод для возврата метаданных для.  
  
 `pClass`  
 [out] Указатель на маркер TypeDef, который представляет тип, реализующий метод.  
  
 `szMethod`  
 [out] Указатель на буфер, имеет имя метода.  
  
 `cchMethod`  
 [in] Запрошенный размер `szMethod`.  
  
 `pchMethod`  
 [out] Указатель на размер в расширенных символах с `szMethod`, или в случае усечения фактическое число расширенных символов в имени метода.  
  
 `pdwAttr`  
 [out] Указатель на любой флаги, связанные с методом.  
  
 `ppvSigBlob`  
 [out] Указатель на двоичную подпись метаданных метода.  
  
 `pcbSigBlob`  
 [out] Указатель на размер в байтах `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Указатель на относительный виртуальный адрес метода.  
  
 `pdwImplFlags`  
 [out] Указатель на любой флаги реализации метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
