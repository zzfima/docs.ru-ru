---
title: Таблица значений по умолчанию (справочник по C#)
description: Узнайте, что такое значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218794"
---
# <a name="default-values-table-c-reference"></a>Таблица значений по умолчанию (справочник по C#)

В следующей таблице показаны значения по умолчанию для типов значений, возвращаемых конструкторами по умолчанию. Конструкторы по умолчанию вызываются с помощью оператора `new`, как показано ниже:

```csharp
int myInt = new int();
```

Приведенная выше инструкция приводит к тому же результату, что и следующая:

```csharp
int myInt = 0;
```

Обратите внимание, что в C# не допускается использование неинициализированных переменных.

|Тип значения|Значение по умолчанию|
|----------------|-------------------|
|[bool](bool.md)|`false`|
|[byte](byte.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0,0D|
|[enum](enum.md)|Значение, создаваемое выражением (E)0, где E — это идентификатор перечисления.|
|[float](float.md)|0,0F|
|[int](int.md)|0|
|[long](long.md)|0L|
|[sbyte](sbyte.md)|0|
|[short](short.md)|0|
|[struct](struct.md)|Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.|
|[uint](uint.md)|0|
|[ulong](ulong.md)|0|
|[ushort](ushort.md)|0|

## <a name="see-also"></a>См. также
 [Справочник по C#](../index.md)  
 [Руководство по программированию на C#](../../programming-guide/index.md)  
 [Таблица типов значений](value-types-table.md)  
 [Типы значений](value-types.md)  
 [Таблица встроенных типов](built-in-types-table.md)  
 [Справочные таблицы по типам](reference-tables-for-types.md)
