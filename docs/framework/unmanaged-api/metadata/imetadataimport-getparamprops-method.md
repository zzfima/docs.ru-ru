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
ms.workload: dotnet
ms.openlocfilehash: f393ccd6296cb06498b30a29c7ea55f088e0a393
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
