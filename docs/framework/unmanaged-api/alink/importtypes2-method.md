---
title: Метод ImportTypes2
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2958fe31ff0065cfb028eaddf8bbb02f3618f9d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471736"
---
# <a name="importtypes2-method"></a>Метод ImportTypes2
Инициирует импорт типов. Вызовите этот метод, чтобы начать импорт типов из каждой области, импортированной с помощью [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки, в который планируется импортировать.  
  
 `FileToken`  
 Идентификатор файла, из которого импортируются.  
  
 `dwScope`  
 Отсчитываемый от нуля область, из которого импортируются.  
  
 `phEnum`  
 Получает дескриптор перечислителя для типов в заданной области.  
  
 `ppImportScope`  
 При необходимости получает [интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) интерфейс.  
  
 `pdwCountOfTypes`  
 При необходимости получает число типов в указанной области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
