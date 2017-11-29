---
title: "Метод GetScope2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetScope2
api_location: alink.dll
api_type: COM
f1_keywords: GetScope2
helpviewer_keywords: GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 143d1d7cfd6f99a662fd7a79e2e2fa629f74967a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="getscope2-method"></a>Метод GetScope2
Возвращает область импортирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
#### <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор целевой сборки.  
  
 `FileToken`  
 Идентификатор файла, из которого требуется импортировать.  
  
 `dwScope`  
 Отсчитываемый от нуля область для импорта.  
  
 `ppImportScope`  
 Получает указатель на [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) интерфейс для указанной области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink-интерфейс API](../../../../docs/framework/unmanaged-api/alink/index.md)
