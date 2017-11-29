---
title: "Метод IMetaDataImport::GetParamProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f36282df52b316bfa32c50c3fa9f55f829aa04e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamprops-method"></a>Метод IMetaDataImport::GetParamProps
Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tk`  
 [in] Токен ParamDef, который представляет метаданные для возвращаемого параметра.  
  
 `pmd`  
 [out] Указатель на токен MethodDef, предоставляющий метод, который принимает параметр.  
  
 `pulSequence`  
 [out] Порядковый номер параметра в списке аргументов метода.  
  
 `szName`  
 [out] Буфер для хранения имени параметра.  
  
 `cchName`  
 [in] Запрошенный размер в расширенных символах с `szName`.  
  
 `pchName`  
 [out] Возвращаемый размер в расширенных символах с `szName`.  
  
 `pdwAttr`  
 [out] Указатель на любой атрибут флаги, связанные с параметром.  
  
 `pdwCPlusTypeFlag`  
 [out] Указатель на флаг, определяют, параметр <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Указатель на строковую константу, возвращаемых параметром.  
  
 `pcchValue`  
 [out] Размер `ppValue` в расширенные символы, или нуль, если `ppValue` не содержит строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
