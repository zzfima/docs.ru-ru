---
title: Метод ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777116"
---
# <a name="importfileex-method"></a>Метод ImportFileEx
Импортирует указанную сборку или непривязанный модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `pszFilename`  
 Полное имя файла, из которого необходимо выполнить импорт.  
  
 `pszTargetName`  
 Необязательное имя целевого файла.  
  
 `fSmartImport`  
 Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.  
  
 `dwOpenFlags`  
 Флаги, передаваемые в [метод OpenScope](../metadata/imetadatadispenser-openscope-method.md).  
  
 `pImportToken`  
 Получает идентификатор импортируемого файла.  
  
 `ppAssemblyScope`  
 Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) для области импорта сборки. Имеет значение NULL, если файл не является сборкой.  
  
 `pdwCountOfScopes`  
 Получает число импортированных файлов и (или) областей.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается с ошибкой, возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
