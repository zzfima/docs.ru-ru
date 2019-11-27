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
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448783"
---
# <a name="isymunmanagedmethod-interface"></a>Интерфейс ISymUnmanagedMethod
Представляет метод в хранилище символов. Этот интерфейс предоставляет доступ только к атрибутам метода, относящимся к символам, а не к атрибутам, связанным с типом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|Возвращает пространство имен, в котором определен этот метод.|  
|[Метод GetOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|Возвращает смещение в этом методе, соответствующее заданной позиции в документе.|  
|[Метод GetParameters](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|Возвращает параметры для этого метода.|  
|[Метод GetRanges](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|При наличии позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам промежуточного языка MSIL, которые находятся в этом методе.|  
|[Метод GetRootScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|Возвращает корневую лексическую область внутри этого метода. Эта область включает весь метод.|  
|[Метод GetScopeFromOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|Возвращает наиболее окружающую лексическую область внутри этого метода, которая заключает заданное смещение.|  
|[Метод GetSequencePointCount](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|Возвращает число точек следования в этом методе.|  
|[Метод GetSequencePoints](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|Возвращает все точки следования в этом методе.|  
|[Метод GetSourceStartEnd](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|Возвращает начальную и конечную позиции документа для источника данного метода.|  
|[Метод GetToken](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|Возвращает маркер метаданных для этого метода.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
