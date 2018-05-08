---
title: Интерфейс ISymUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 728acc09f739fe567fca4a2571cbabf1ba8838a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedmethod-interface"></a>Интерфейс ISymUnmanagedMethod
Представляет метод в хранилище символов. Этот интерфейс предоставляет доступ к только связанные с symbol атрибуты метода, вместо атрибутов, связанных с типами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|Возвращает пространство имен, в котором определен этот метод.|  
|[Метод GetOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|Возвращает смещение в этом методе, соответствующее заданной позиции в документе.|  
|[Метод GetParameters](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|Получает параметры для этого метода.|  
|[Метод GetRanges](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|Заданной позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам на языке MSIL занимаемым данной позицией в этом методе.|  
|[Метод GetRootScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|Возвращает корневую лексическую область в этом методе. Эта область включает весь метод.|  
|[Метод GetScopeFromOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|Возвращает наиболее узкая Внешняя лексическая область в этом методе, содержащую данное смещение.|  
|[Метод GetSequencePointCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|Возвращает число точек следования в методе.|  
|[Метод GetSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|Возвращает все точки следования в методе.|  
|[Метод GetSourceStartEnd](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|Возвращает начальную и конечную позицию документа источника этого метода.|  
|[Метод GetToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|Возвращает токен метаданных для этого метода.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
