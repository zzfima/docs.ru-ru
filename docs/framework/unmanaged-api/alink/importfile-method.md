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
ms.openlocfilehash: 54b0a02af7f22e775e3f9567de79664c9805b4e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
 Необязательное имя файла вывода, можно использовать для переименования файла, он связан в сборку.  
  
 `fSmartImport`  
 Значение TRUE, если используется ImportTypes, в противном случае импорт должно выполняться вручную.  
  
 `pImportToken`  
 Указатель на маркер, в котором будет храниться уникальный идентификатор файла. Это может быть файл сборки или файл.  
  
 `ppAssemblyScope`  
 Получает указатель на [imetadataassemblyimport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md). Может иметь значение NULL, если файл не является сборкой.  
  
 `pdwCountOfScopes`  
 Указатель на число файлов и/или областей, которые были импортированы.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
