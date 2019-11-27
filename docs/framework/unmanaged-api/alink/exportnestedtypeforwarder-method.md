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
ms.openlocfilehash: cc81ccd1c754e3d34c54737f4560b4f81d5cc916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438414"
---
# <a name="exportnestedtypeforwarder-method"></a>Метод ExportNestedTypeForwarder
Добавляет сервер пересылки типа для вложенного типа в таблицу типов данной сборки.  
  
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
 Идентификатор сборки, из которой необходимо выполнить экспорт.  
  
 `FileToken`  
 Маркер файла или идентификатор сборки файла, который определяет тип.  
  
 `TypeToken`  
 Токен для типа.  
  
 `ParentType`  
 Токен родительского типа.  
  
 `pszTypename`  
 Полное имя типа для экспорта.  
  
 `dwFlags`  
 `ComType` флаги, такие как `tdPublic` или `tdNested`.  
  
 `pType`  
 Получает маркер типа экспорта. Это необходимо только для выпуска вложенных типов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
