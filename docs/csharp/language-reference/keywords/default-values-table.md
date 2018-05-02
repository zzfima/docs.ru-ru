---
title: Таблица значений по умолчанию (справочник по C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
