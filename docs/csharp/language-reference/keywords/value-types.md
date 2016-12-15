---
title: "Типы значений (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.valuetypes"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, типы значений"
  - "типы [C#], типы значений"
  - "типы значений [C#]"
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Типы значений (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Типы значений состоят из двух основных категорий:  
  
-   [Структуры](../../../csharp/language-reference/keywords/struct.md)  
  
-   [Перечисления](../../../csharp/language-reference/keywords/enum.md)  
  
 Структуры делятся на следующие категории:  
  
-   Числовые типы  
  
    -   [Целочисленные типы](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [Типы с плавающей запятой](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   Пользовательские структуры.  
  
## Основные характеристики типов значений  
 Переменные, основанные на типах значений, содержат непосредственно значения.  При присвоении переменной одного типа значений другому создается копия присваиваемого значения.  В этом заключается отличие от переменных ссылочного типа, при присвоении которых копируются ссылки на объекты, но не сами объекты.  
  
 Все типы значений являются неявными производными от <xref:System.ValueType?displayProperty=fullName>.  
  
 В отличие от ссылочных типов, новый производный тип из типа значения создать нельзя.  Однако, как и в ссылочных типах, структуры могут реализовывать интерфейсы.  
  
 В отличие от ссылочных типов тип значения не может содержать значение `null`.  Однако функция [тип, допускающий значение null](../../../csharp/programming-guide/nullable-types/index.md) допускает типы значения, которое необходимо присвоить `null`.  
  
 Для каждого типа значений существует неявный конструктор по умолчанию, инициализирующий значение по умолчанию для данного типа..  Дополнительные сведения о значениях по умолчанию типов значений см. в [таблице значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## Основные характеристики простых типов  
 Все простые типы — встроенные в язык C\# — являются псевдонимами системных типов .NET Framework.  Например, [int](../../../csharp/language-reference/keywords/int.md) является псевдонимом для <xref:System.Int32?displayProperty=fullName>.  Полный список значений псевдонимов см. в разделе [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md).  
  
 Константные выражения, все операнды которых являются константами простых типов, вычисляются при компиляции.  
  
 Простые типы можно инициализировать с помощью литералов.  Например, "A" — это литерал типа `char`, а 2001 — литерал типа `int`.  
  
## Инициализация типов значений  
 Локальные переменные в C\# должны быть инициализированы перед использованием.  Например, можно объявить локальную переменную без инициализации, как показано в следующем примере:  
  
```  
int myInt;  
```  
  
 Однако ее нельзя использовать без инициализации.  Для инициализации используется следующий оператор:  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Этот оператор эквивалентен следующему оператору:  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 Разумеется, можно разместить объявление и инициализацию в одном и том же операторе, как показано в следующих примерах.  
  
```  
int myInt = new int();  
```  
  
 —либо—  
  
```  
int myInt = 0;  
```  
  
 Оператор [new](../../../csharp/language-reference/keywords/new.md) вызывает конструктор определенного типа по умолчанию и присваивает переменной значение по умолчанию.  В предыдущем примере конструктор по умолчанию присвоил значение `0` переменной `myInt`.  Дополнительные сведения о значениях, присваиваемых путем вызова конструкторов по умолчанию см. в [таблице значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 При наличии пользовательских типов используйте [new](../../../csharp/language-reference/keywords/new.md) для вызова конструктора по умолчанию.  В следующем примере кода вызывается конструктор по умолчанию структуры `Point`.  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 После вызова структура считается окончательно присвоенной, все ее члены инициализируются со значениями по умолчанию.  
  
 Дополнительные сведения об операторе new см. в разделе [new](../../../csharp/language-reference/keywords/new.md).  
  
 Сведения о форматировании результатов числовых типов см. в разделе [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [Справочные таблицы по типам](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)