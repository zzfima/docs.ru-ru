---
title: Метод ImportFile
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 116ed60dab3365cac052d3b13ce7b056caca0452
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619688"
---
# <a name="importfile-method"></a>Метод ImportFile
Импортирует сборок и несвязанных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszFilename`  
 Полное имя файла для импорта.  
  
 `pszTargetName`  
 Необязательный выходной имя файла, который может использоваться для переименования файла, так как он связан в сборку.  
  
 `fSmartImport`  
 Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.  
  
 `pImportToken`  
 Указатель на маркер, где будет храниться уникальный идентификатор файла. Файл может быть сборки или файла.  
  
 `ppAssemblyScope`  
 Получает указатель на [интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). Может иметь значение NULL, если файл не является сборкой.  
  
 `pdwCountOfScopes`  
 Указатель на количество файлов и/или области, которые были импортированы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
