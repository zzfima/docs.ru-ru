---
title: Типы значений (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: fdda6942c6883baaaea5e305a1e699a01e707d2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="value-types-c-reference"></a>Типы значений (Справочник по C#)
Типы значений относятся к двум основным категориям:  
  
-   [Структуры](../../../csharp/language-reference/keywords/struct.md)  
  
-   [Перечисления](../../../csharp/language-reference/keywords/enum.md)  
  
 Структуры делятся на следующие категории:  
  
-   Числовые типы  
  
    -   [Целочисленные типы](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [Типы с плавающей запятой](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   Определяемые пользователем структуры.  
  
## <a name="main-features-of-value-types"></a>Основные возможности типов значений  
 Переменные, основанные на типах значений, непосредственно содержат значения. Если присвоить одну переменную типа значения другой, в нее будет скопировано содержащееся в исходной переменной значение. В этом заключается отличие от присвоения переменных ссылочного типа, при котором копируется не сам объект, а ссылка на него.  
  
 Все типы значения являются неявными производными от <xref:System.ValueType?displayProperty=nameWithType>.  
  
 В отличие от ссылочных типов, создать новый производный от типа значения тип нельзя. Тем не менее, как и ссылочные типы, структуры могут реализовывать интерфейсы.  
  
 В отличие от ссылочных типов, тип значения не может содержать значение `null`. Тем не менее с помощью [типов, допускающих значение null](../../../csharp/programming-guide/nullable-types/index.md), можно присваивать типы значений значениям `null`.  
  
 Каждый тип значения имеет неявный конструктор по умолчанию, который инициализирует значение по умолчанию для этого типа. Дополнительные сведения о значениях по умолчанию для типов значений см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## <a name="main-features-of-simple-types"></a>Основные возможности простых типов  
 Все простые типы, реализованные в языке C#, являются псевдонимами системных типов платформы .NET. Например, [int](../../../csharp/language-reference/keywords/int.md) является псевдонимом типа <xref:System.Int32?displayProperty=nameWithType>. Полный список псевдонимов см. в разделе [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md).  
  
 Константные выражения, операнды которых являются константами простого типа, вычисляются во время компиляции.  
  
 Простые типы можно инициализировать с помощью литералов. Например, "A" — это литерал типа `char`, а "2001" — литерал типа `int`.  
  
## <a name="initializing-value-types"></a>Инициализация типов значений  
 В языке C# локальные переменные необходимо инициализировать перед использованием. Например, можно объявить локальную переменную без инициализации, как показано в следующем примере:  
  
```  
int myInt;  
```  
  
 Тем не менее использовать ее до инициализации нельзя. Для инициализации локальной переменной можно использовать следующую инструкцию:  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Эта инструкция эквивалентна следующей:  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 При необходимости объявление и инициализация могут быть выполнены в одной инструкции, как показано в следующем примере:  
  
```  
int myInt = new int();  
```  
  
 – или –  
  
```  
int myInt = 0;  
```  
  
 Инструкция [new](../../../csharp/language-reference/keywords/new.md) вызывает конструктор по умолчанию для конкретного типа и присваивает переменной значение по умолчанию. В предыдущем примере конструктор по умолчанию присваивает значение `0` переменной `myInt`. Дополнительные сведения о значениях, присваиваемых путем вызова конструктора по умолчанию, см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Для определяемых пользователем типов инструкция [new](../../../csharp/language-reference/keywords/new.md) вызывает конструктор по умолчанию. Например, следующая инструкция вызывает конструктор по умолчанию для структуры `Point`:  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 После этого вызова структура считается определенно присвоенной, то есть все ее элементы будут инициализированы и получат значения по умолчанию.  
  
 Дополнительные сведения об операторе new см. в [этом разделе](../../../csharp/language-reference/keywords/new.md).  
  
 Дополнительные сведения о форматировании выходных данных числовых типов см. в разделе [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Типы](../../../csharp/language-reference/keywords/types.md)  
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)
