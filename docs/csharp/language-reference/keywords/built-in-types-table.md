---
title: Справочник по C#. Таблица встроенных типов
description: Ключевые слова для встроенных типов C#
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 1836458972c453b733287e58e783f32892d27fde
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964385"
---
# <a name="built-in-types-table-c-reference"></a>Таблица встроенных типов (Справочник по C#)

В следующей таблице показаны ключевые слова для встроенных типов C#, которые являются псевдонимами предопределенных типов в пространстве имен <xref:System>:

|Тип C#|Тип .NET|  
|--------------|-------------------------|  
|[bool](../builtin-types/bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](../builtin-types/char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](../builtin-types/reference-types.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](../builtin-types/reference-types.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>Примечания

Все типы в таблице, за исключением `object` и `string`, считаются простыми.

Типы .NET и псевдонимы ключевых слов типов C# являются взаимозаменяемыми. Например, можно объявить целочисленную переменную с помощью любого из следующих объявлений:

```csharp
int x = 123;
System.Int32 y = 123;
```

Используйте оператор [typeof](../operators/type-testing-and-cast.md#typeof-operator), чтобы получить экземпляр <xref:System.Type?displayProperty=nameWithType>, представляющий указанный тип:

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Типы значений](value-types.md)
- [Ссылочные типы](reference-types.md)
- [Значения по умолчанию типов C#](../builtin-types/default-values.md)
- [dynamic](../builtin-types/reference-types.md#the-dynamic-type)
