---
title: Метод EnumImportTypes
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789959"
---
# <a name="enumimporttypes-method"></a>Метод EnumImportTypes

Перечисляет каждый тип в каждой области.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>Параметры

`hEnum`\
Дескриптор для перечислителя.

`dwMax`\
Максимальное число извлекаемых типов.

`aTypeDefs`\
Получает тип токенов, оно не должно превышать `dwMax`.

`pdwCount`\
Получает фактическое число типов в `aTypeDefs`.

## <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK, если метод выполнен успешно.

## <a name="requirements"></a>Требования

Требуется alink.h

## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)