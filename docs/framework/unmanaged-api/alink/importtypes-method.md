---
title: Метод ImportTypes
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 76d2b163f959111923bffb1348890f6fbb29828e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445677"
---
# <a name="importtypes-method"></a>Метод ImportTypes
Инициирует импорт типов из каждой области, импортированной с помощью [метода ImportFile](importfile-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки, в которую необходимо выполнить импорт.  
  
 `FileToken`  
 Идентификатор файла, из которого необходимо выполнить импорт.  
  
 `dwScope`  
 Отсчитываемая от нуля область для импорта.  
  
 `phEnum`  
 Получает обработчики перечислителя для типов в этой области.  
  
 `ppImportScope`  
 При необходимости получает интерфейс [интерфейса IMetaDataImport](../metadata/imetadataimport-interface.md) .  
  
 `pdwCountOfTypes`  
 При необходимости получает число типов в указанной области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
