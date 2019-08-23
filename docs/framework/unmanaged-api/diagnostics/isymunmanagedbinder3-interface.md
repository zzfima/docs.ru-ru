---
title: Интерфейс ISymUnmanagedBinder3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6f514cc070a0a38eb09a5387efc8611100765b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944094"
---
# <a name="isymunmanagedbinder3-interface"></a>Интерфейс ISymUnmanagedBinder3
Расширяет интерфейс связывателя символов. Получите этот интерфейс, вызвав метод `QueryInterface` для объекта, который `ISymUnmanagedBinder` реализует интерфейс.  
  
> [!IMPORTANT]
> При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|Позволяет пользователю реализовать или предоставить через обратный вызов либо `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` для получения сведений о каталоге отладки из памяти.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [Интерфейс ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
