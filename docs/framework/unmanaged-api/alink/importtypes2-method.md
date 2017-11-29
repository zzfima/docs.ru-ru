---
title: "Метод ImportTypes2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportTypes2
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes2
helpviewer_keywords: ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d707cdd827b5e435c961a14e67170ab0e2bc90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes2-method"></a>Метод ImportTypes2
Инициирует импорт типов. Вызовите этот метод, чтобы начать импорт типов из каждой области, импортированной посредством [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).  
  
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
  
#### <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки, в который планируется импортировать.  
  
 `FileToken`  
 Идентификатор файла, из которого требуется импортировать.  
  
 `dwScope`  
 Отсчитываемый от нуля область, из которого требуется импортировать.  
  
 `phEnum`  
 Получает дескриптор перечислителя для типов в заданной области.  
  
 `ppImportScope`  
 При необходимости получает [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) интерфейс.  
  
 `pdwCountOfTypes`  
 При необходимости получает число типов в указанной области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink-интерфейс API](../../../../docs/framework/unmanaged-api/alink/index.md)
