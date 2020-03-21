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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179416"
---
# <a name="exportnestedtype-method"></a>Метод ExportNestedType
Определяет вложенные типы как экспортируемые. [Метод ExportType](exporttype-method.md) также может экспортировать вложенные типы, но этот метод быстрее.  
  
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
 Идентификатор сборки для экспорта с.  
  
 `FileToken`  
 Файл токен или сборка файла, определяющий тип, который будет экспортироваться.  
  
 `TypeToken`  
 Введите токен типа, который будет экспортироваться.  
  
 `ParentType`  
 Токен родительского типа.  
  
 `pszTypename`  
 Полностью квалифицированное название типа для экспорта.  
  
 `dwFlags`  
 `ComType`флаги, `tdPublic` `tdNested`такие как или . Это значение может быть передано [методу DefineExportedType.](../metadata/imetadataassemblyemit-defineexportedtype-method.md)  
  
 `pType`  
 Получает токен для экспортируемого типа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK, если метод успешно.  
  
## <a name="requirements"></a>Требования  
 Требуетa alink.h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
