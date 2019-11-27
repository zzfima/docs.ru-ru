---
title: Интерфейс ISymUnmanagedBinder
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
ms.openlocfilehash: f23df98abc5355f0b25d7253b5f2ae808b3446a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449369"
---
# <a name="isymunmanagedbinder-interface"></a>Интерфейс ISymUnmanagedBinder
Представляет связыватель символов для неуправляемого кода.  
  
> [!IMPORTANT]
> При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|При наличии интерфейса метаданных и имени файла возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы, связанные с модулем.|  
|[Метод GetReaderFromStream](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|При наличии интерфейса метаданных и потока, содержащего хранилище символов, возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы из заданного хранилища символов.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedBinder2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [Интерфейс ISymUnmanagedBinder3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
