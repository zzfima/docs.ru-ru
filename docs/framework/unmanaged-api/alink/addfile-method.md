---
title: Метод AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446681"
---
# <a name="addfile-method"></a>Метод AddFile
Добавляет файлы в сборку. Также можно использовать для создания непривязанных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Уникальный идентификатор сборки, подлежащая дополну.  
  
 `pszFilename`  
 Полное имя добавляемого файла.  
  
 `dwFlags`  
 Флаги COM+ Филедеф, такие как `ffContainsNoMetaData` и `ffWriteable`. `dwFlags` передается в [метод дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Интерфейс [IMetaDataEmit](../metadata/imetadataemit-interface.md) , используемый для выдачи метаданных при необходимости.  
  
 `pFileToken`  
 Указатель на место, где будет храниться уникальный идентификатор добавленного файла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
