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
ms.openlocfilehash: f8dd1daf3528bbc642033e254a809c18c3662ff1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779186"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>Метод IMetaDataAssemblyImport::GetExportedTypeProps
Получает набор свойств экспортируемого типа с заданной подписью метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="parameters"></a>Параметры  
 `mdct`  
 [in] `mdExportedType` Маркер метаданных, представляющий экспортированный тип.  
  
 `szName`  
 [out] Имя экспортируемого типа.  
  
 `cchName`  
 [in] Размер в расширенные символы из `szName`.  
  
 `pchName`  
 [out] Число расширенных символов, фактически возвращенных в `szName`  
  
 `ptkImplementation`  
 [out] `mdFile`, `mdAssemblyRef`, Или `mdExportedType` токен метаданных, который содержит или разрешает доступ к свойствам экспортируемого типа.  
  
 `ptkTypeDef`  
 [out] Указатель на `mdTypeDef` токен, представляющий тип в файле.  
  
 `pdwExportedTypeFlags`  
 [out] Указатель на флаги, описывающие метаданные, применяемые к экспортированный тип. Флаги значение может быть один или несколько [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) значения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
