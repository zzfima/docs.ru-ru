---
title: "Метод SetNonAssemblyFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetNonAssemblyFlags
api_location: alink.dll
api_type: COM
f1_keywords: SetNonAssemblyFlags
helpviewer_keywords: SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5f8761259e89b4befd0eeaf893ffbe5d4142350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="setnonassemblyflags-method"></a>Метод SetNonAssemblyFlags
Задает флаги, не зависящие от сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a>Параметры  
 `afFlags`  
 Флаги ALink.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [ALink-интерфейс API](../../../../docs/framework/unmanaged-api/alink/index.md)
