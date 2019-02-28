---
title: Метод AddImport
ms.date: 03/30/2017
api_name:
- AddImport
- IALink.AddImport
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddImport
helpviewer_keywords:
- AddImport method
ms.assetid: 4fedf8a0-08c8-43d0-aa00-20f2a521c991
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95a434cc365e12aa19d164951726ddad8945f60d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974137"
---
# <a name="addimport-method"></a>Метод AddImport
Добавляет импортирует в сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Уникальный идентификатор сборки, которую необходимо дополнить.  
  
 `ImportToken`  
 Уникальный идентификатор, полученный из [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), файла для импорта.  
  
 `dwFlags`  
 Флаги FileDef COM +, таких как `ffContainsNoMetaData` и `ffWriteable`. `dwFlags` передается [метод DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Указатель на маркер, который получает идентификатор для результирующего файла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
