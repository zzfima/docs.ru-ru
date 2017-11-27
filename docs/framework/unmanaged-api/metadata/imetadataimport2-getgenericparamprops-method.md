---
title: "Метод IMetaDataImport2::GetGenericParamProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af6ab8fd6e941f5219c1aad2946479dda0b64264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a>Метод IMetaDataImport2::GetGenericParamProps
Возвращает метаданные, связанные с универсальным параметром, представленного указанным токеном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `gp`  
 [in] Токен, представляющий универсальный параметр, для которого возвращаются метаданные.  
  
 `pulParamSeq`  
 [out] Порядковый номер `Type` параметра в родительский конструктор или метод.  
  
 `pdwParamFlags`  
 [out] Значение [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) перечисление, описывающее `Type` универсального параметра.  
  
 `ptOwner`  
 [out] Токен TypeDef или MethodDef, представляющий владельца параметра.  
  
 `reserved`  
 [out] Зарезервировано для будущего расширения.  
  
 `wzName`  
 [out] Имя универсального параметра.  
  
 `cchName`  
 [in] Размер `wzName` буфера.  
  
 `pchName`  
 [out] Возвращаемый размер имя в расширенных символов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
