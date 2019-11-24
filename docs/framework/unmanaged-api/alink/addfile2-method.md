---
title: Метод AddFile2
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: 8dadf9ec8f896b03e4918b21f5153c1b747010fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446667"
---
# <a name="addfile2-method"></a>Метод AddFile2
Adds files to the assembly. Can also be used to create unbound modules.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 ID for the assembly to which the file is added.  
  
 `pszFilename`  
 Name of the file to be added.  
  
 `dwFlags`  
 COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`. `dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.  
  
 `pFileToken`  
 Receives ID for the file being added.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Returns S_OK if the method succeeds.  
  
## <a name="requirements"></a>Требования  
 Requires alink.h.  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
