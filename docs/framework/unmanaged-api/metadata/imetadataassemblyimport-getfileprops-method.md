---
title: "Метод IMetaDataAssemblyImport::GetFileProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c4ca64d4781f0cc228c0af7f2ae772098d2f164a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>Метод IMetaDataAssemblyImport::GetFileProps
Получает свойства файла с заданной подписью метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mdf`  
 [in] `mdFile` Токен метаданных, который представляет файл, для которого нужно получить свойства.  
  
 `szName`  
 [out] Простое имя файла.  
  
 `cchName`  
 [in] Размер в расширенных символов из `szName`.  
  
 `pchName`  
 [out] Число расширенных символов, фактически извлеченных в `szName`.  
  
 `ppbHashValue`  
 [out] Указатель с хэш-значением. Это хэш, с помощью алгоритма SHA-1, файла.  
  
 `pcbHashValue`  
 [out] Число расширенных символов в возвращенное хэш-значение.  
  
 `pdwFileFlags`  
 [out] Указатель флаги, описывающие метаданные, применяемые в файл. Значение флагов представляет собой сочетание одного или нескольких [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) значения.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Imetadataassemblyimport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
