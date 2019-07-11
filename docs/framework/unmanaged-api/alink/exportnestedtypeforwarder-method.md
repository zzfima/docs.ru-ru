---
title: Метод ExportNestedTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb8fba433c5f7ef9701caf61971841672f46b425
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742037"
---
# <a name="exportnestedtypeforwarder-method"></a>Метод ExportNestedTypeForwarder
Добавляет метод передачи типа для вложенного типа в таблицу типов данной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  
 `AssemblyID`  
 Идентификатор сборки для экспорта.  
  
 `FileToken`  
 Идентификатор маркера или сборки файла, который определяет тип файла.  
  
 `TypeToken`  
 Токен для типа.  
  
 `ParentType`  
 Маркер родительского типа.  
  
 `pszTypename`  
 Полное имя типа для экспорта.  
  
 `dwFlags`  
 `ComType` флаги, такие как `tdPublic` или `tdNested`.  
  
 `pType`  
 Получает токен типа экспорта. Это необходимо только для выдачи вложенных типов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 Требуется alink.h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Интерфейс IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
