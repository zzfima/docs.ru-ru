---
title: Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d3bc8b00b568f96cd55b7811f310d34c1ff700d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a>Метод ISymUnmanagedWriter5::OpenMapTokensToSourceSpans
Откройте раздел специальные пользовательские данные для передачи сведений о сопоставлении span токен источника в. Когда метод уже открыт, или наоборот, возникает ошибка при открытии в этом разделе.  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ISymUnmanagedWriter5](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
