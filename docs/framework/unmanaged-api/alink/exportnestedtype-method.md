---
title: Метод ExportNestedType
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
ms.openlocfilehash: fded6b95144d4088a2abc8dfcc4ef8eda331c34f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438420"
---
# <a name="exportnestedtype-method"></a>Метод ExportNestedType
Указывает вложенные типы как экспортируемые. [Метод ExportType](exporttype-method.md) также может экспортировать вложенные типы, но этот метод выполняется быстрее.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExportNestedType(  
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
 Идентификатор сборки, из которой производится экспорт.  
  
 `FileToken`  
 Маркер файла или сборка файла, определяющая тип, который должен быть сделан экспортируемым.  
  
 `TypeToken`  
 Токен типа, который должен быть доступен для экспорта.  
  
 `ParentType`  
 Токен родительского типа.  
  
 `pszTypename`  
 Полное имя типа для экспорта.  
  
 `dwFlags`  
 `ComType` флаги, такие как `tdPublic` или `tdNested`. Это значение может быть передано [методу дефиникспортедтипе](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Получает токен для экспортируемого типа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  
 Требуется ALink. h  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
