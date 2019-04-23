---
title: Интерфейс ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4474269688094ea6c81b06659727acfb9c2ad6c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095715"
---
# <a name="isymencunmanagedmethod-interface"></a>Интерфейс ISymENCUnmanagedMethod
Предоставляет сведения для "Изменить и продолжить".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDocumentsForMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|Возвращает документы, которые этот метод имеет строки.|  
|[Метод GetDocumentsForMethodCount](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Возвращает количество документов, этот метод имеет строки.|  
|[Метод GetFileNameFromOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|Получает имя файла для строки, связанной со смещением.|  
|[Метод GetLineFromOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|Получает сведения о строке, связанной со смещением.|  
|[Метод GetSourceExtentInDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|Получает наименьшую начальную строку и наибольшую конечную строку метода в определенном документе.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
