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
ms.openlocfilehash: aed70a78e2513f4d63fbf8ca8868f26efbac9ae8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787665"
---
# <a name="addimport-method"></a>Метод AddImport
Добавляет в сборку импорты.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AddImport(  
    mdAssembly      AssemblyID,  
    mdToken         ImportToken,  
    DWORD           dwFlags,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Уникальный идентификатор сборки для дополнения.  
  
 `ImportToken`  
 Уникальный идентификатор, полученный из [метода ImportFile](importfile-method.md)импортируемого файла.  
  
 `dwFlags`  
 COM+ филедеф флаги, `ffContainsNoMetaData` такие `ffWriteable`как и. `dwFlags`передается [методу дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Указатель на токен, который получает идентификатор для результирующего файла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается с ошибкой, возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
