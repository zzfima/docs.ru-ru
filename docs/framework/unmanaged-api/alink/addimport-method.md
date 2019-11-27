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
ms.openlocfilehash: 52e52ac62e2dcfeb182da3014a863409f640274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446653"
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
 Флаги COM+ Филедеф, такие как `ffContainsNoMetaData` и `ffWriteable`. `dwFlags` передается в [метод дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pFileToken`  
 Указатель на токен, который получает идентификатор для результирующего файла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
