---
title: Интерфейс ISymUnmanagedSourceServerModule
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a63700abf77d56134ca30620033c398af735599
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedsourceservermodule-interface"></a>Интерфейс ISymUnmanagedSourceServerModule
Предоставляет данные сервера источника для модуля. Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetSourceServerData](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|Возвращает данные исходного сервера для модуля.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
