---
title: Метод IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c76e46c75680d9fc0ad70e94da288f0c6b5e5ee1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>Метод IMetaDataAssemblyImport::GetExportedTypeProps
Возвращает набор свойств экспортируемого типа с заданной подписью метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `mdct`  
 [in] `mdExportedType` Токен метаданных, представляющий экспортируемого типа.  
  
 `szName`  
 [out] Имя экспортируемого типа.  
  
 `cchName`  
 [in] Размер в расширенные символы из `szName`.  
  
 `pchName`  
 [out] Число расширенных символов, фактически извлеченных в `szName`  
  
 `ptkImplementation`  
 [out] `mdFile`, `mdAssemblyRef`, Или `mdExportedType` токен метаданных, который содержит или разрешает доступ к свойствам экспортируемого типа.  
  
 `ptkTypeDef`  
 [out] Указатель на `mdTypeDef` токен, представляющий тип в файле.  
  
 `pdwExportedTypeFlags`  
 [out] Указатель флаги, описывающие метаданные, применяемые к экспортируемого типа. Значение флагов может быть один или несколько [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) значения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
