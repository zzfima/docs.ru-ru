---
title: Справочник по C#. Таблица встроенных типов
ms.custom: seodec18
description: Ключевые слова для встроенных типов C#
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: d93176b850d84753106accef3bcaedab38f4ddc7
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306798"
---
# <a name="built-in-types-table-c-reference"></a>Таблица встроенных типов (Справочник по C#)

В следующей таблице показаны ключевые слова для встроенных типов C#, которые являются псевдонимами предопределенных типов в пространстве имен <xref:System>.  
  
|Тип C#|Тип .NET|  
|--------------|-------------------------|  
|[bool](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>Примечания

Все типы в таблице, за исключением `object` и `string`, считаются простыми.  
  
Ключевые слова типов C# и их псевдонимы являются взаимозаменяемыми. Например, можно объявить целочисленную переменную с помощью любого из следующих объявлений:  

```csharp
int x = 123;
System.Int32 y = 123;
```

Используйте оператор [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator), чтобы получить экземпляр <xref:System.Type?displayProperty=nameWithType>, представляющий указанный тип:

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

- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Типы значений](value-types.md)
- [Ссылочные типы](reference-types.md)
- [Таблица значений по умолчанию](default-values-table.md)
- [dynamic](dynamic.md)
