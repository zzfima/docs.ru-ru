---
title: Метод ImportFile2
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3c145bae61922894f4893d532923319ccf16f85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499016"
---
# <a name="importfile2-method"></a>Метод ImportFile2
Импортирует сборок и несвязанных модулей. Этот метод аналогичен [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), но работает, даже если импортируемого файла не существует на диске.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszFilename`  
 Имя файла для импорта.  
  
 `pszTargetName`  
 Необязательный выходной имя файла, который может использоваться для переименования файла, так как он связан в сборку.  
  
 `pAssemblyScopeIn`  
 Дополнительная область [интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс.  
  
 `fSmartImport`  
 Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.  
  
 `pImportToken`  
 Получает идентификатор для файла или сборки.  
  
 `ppAssemblyScope`  
 Получает [интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс. Значение NULL, если файл не является сборкой.  
  
 `pdwCountOfScopes`  
 Получает найденные файлы и/или импортированные области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h.  
  
## <a name="see-also"></a>См. также
- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
