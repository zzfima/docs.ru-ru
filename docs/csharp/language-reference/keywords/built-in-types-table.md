---
title: Таблица встроенных типов (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 7407d18c58dd3d12337c6845627d83f02eaf7fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="built-in-types-table-c-reference"></a>Таблица встроенных типов (Справочник по C#)
В следующей таблице показаны ключевые слова для встроенных типов C#, которые являются псевдонимами предопределенных типов в пространстве имен <xref:System>.  
  
|Тип C#|Тип .NET Framework|  
|--------------|-------------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[object](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a>Примечания  
 Все типы в таблице, за исключением `object` и `string`, считаются простыми.  
  
 Ключевые слова типов C# и их псевдонимы являются взаимозаменяемыми. Например, можно объявить целочисленную переменную с помощью любого из следующих объявлений:  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 Чтобы отобразить фактический тип для любого типа C#, используйте системный метод `GetType()`. Например, следующий оператор выводит системный псевдоним, который представляет тип `myVariable`:  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 Также можно использовать оператор [typeof](../../../csharp/language-reference/keywords/typeof.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)  
 [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
