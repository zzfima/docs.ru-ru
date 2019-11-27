---
title: Интерфейс ISymUnmanagedScope2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 3374097c8d343fed6badf046742ca556d2a92f3e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446227"
---
# <a name="isymunmanagedscope2-interface"></a>Интерфейс ISymUnmanagedScope2
Представляет лексическую область внутри метода. Этот интерфейс расширяет интерфейс [исимунманажедскопе](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) с помощью методов, которые получают сведения о константах, определенных в области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetConstantCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|Возвращает число констант, определенных в этой области.|  
|[Метод GetConstants](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|Возвращает локальные константы, определенные в этой области.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
