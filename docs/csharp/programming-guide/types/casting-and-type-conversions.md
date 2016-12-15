---
title: "Приведение и преобразование типов (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "приведение [C#]"
  - "преобразования [C#], тип"
  - "преобразование типов [C#]"
  - "преобразование типов данных [C#]"
  - "числовые преобразования [C#]"
  - "преобразование типов [С#]"
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
caps.handback.revision: 52
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Приведение и преобразование типов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Поскольку в C\# тип определяется статически тип во время компиляции, после объявления переменной, она не может быть объявлена вновь или использоваться для хранения значений другого типа, если этот тип не преобразуется в тип переменной.  Например, невозможно преобразование из целого числа в произвольную строку.  Поэтому после объявления переменной `i` как целочисленной, нельзя ей присвоить строку "Hello", как показано в следующем коде.  
  
```c#  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 Но иногда может быть необходимым скопировать значение в переменную или параметр метода другого типа.  Например, может быть переменная, которую требуется передать методу, параметр которого имеет тип `double`.  Или может понадобиться присвоить переменную класса переменной типа интерфейса.  Операции такого вида называются *преобразованиями типов*.  В C\# можно выполнять следующие виды преобразований:  
  
-   **Неявные преобразования**. Не требуется никакого специального синтаксиса, поскольку преобразование безопасно для типов и данные не теряются.  Примерами могут служить преобразования от меньшего к большему целому типу, и преобразования из производных классов в базовые классы.  
  
-   **Явные преобразования \(приведения\)**. Для явных преобразований необходим оператор приведения.  Приведение требуется, когда при преобразовании может быть потеряна информация, или когда преобразование может завершиться неудачей по другим причинам. К типичным примерам относится числовое преобразование в тип, который имеет меньшую точность или меньший диапазон значений, а также преобразование экземпляра базового класса в производный класс.  
  
-   **Пользовательские преобразования**. Пользовательские преобразования выполняются специальными методами, которые можно определить для включения явных и неявных преобразований между пользовательскими типами, не имеющих отношения базовый класс — производный класс.  Дополнительные сведения см. в разделе [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
-   **Преобразования с помощью вспомогательных классов**. Для преобразования между несовместимыми типами, например целые числа и объекты <xref:System.DateTime?displayProperty=fullName>, или шестнадцатеричные строки и байтовые массивы, можно использовать класс <xref:System.BitConverter?displayProperty=fullName>, класс <xref:System.Convert?displayProperty=fullName> и методы `Parse` встроенных числовых типов, таких как <xref:System.Int32.Parse%2A?displayProperty=fullName>.  Дополнительные сведения см. в разделах [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) и [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## Неявные преобразования  
 ля встроенных числовых типов неявное преобразование можно выполнить, сохраняемое значение может уместиться в переменной без обрезания или округления до ближайшего.  Например, переменная типа [long](../../../csharp/language-reference/keywords/long.md) \(8\-байтное целое\) может хранить любое значение, которое может хранить [int](../../../csharp/language-reference/keywords/int.md) \(4 байта в 32\-разрядном компьютере\).  В следующем примере компилятор неявно преобразует значение справа в тип `long` перед присвоением его типу `bigNum`.  
  
 [!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 Полный список всех неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Для ссылочных типов всегда существует неявное преобразование из класса в любой из его прямых или косвенных базовых классов или интерфейсов.  Никакого специального синтаксиса не требуется, поскольку производный класс всегда содержит все члены базового класса.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## Явные преобразования  
 Однако если преобразование не может быть выполнено без риска потери данных, для компилятора требуется, чтобы пользователь выполнил явное преобразование, которое называется *приведением*.  Приведение является способом явно указать компилятору, что нужно сделать преобразование, и что известно, что может быть потеря данных.  Для выполнения приведения заключите тип, в который производится приведение, в скобки перед преобразуемым значением или переменной.  Следующая программа выполняет приведение типа [double](../../../csharp/language-reference/keywords/double.md) к типу [int](../../../csharp/language-reference/keywords/int.md).  Без приведения эта программа скомпилирована не будет.  
  
 [!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
 Список разрешенных явных числовых преобразований, см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
 Для ссылочных типов явное приведение необходимо, если нужно выполнить преобразование из базового типа в производный тип:  
  
```c#  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 Операция приведения между ссылочными типами не меняет тип времени выполнения базового объекта; меняется только тип значения, которое используется в качестве ссылки на этот объект.  Дополнительные сведения см. в разделе [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## Исключения преобразования типов во время выполнения  
 В некоторых преобразованиях ссылочного типа компилятор не может определить, допустимо ли приведение.  Для операции приведения возможна корректная ошибка компилятора во время выполнения.  Как показано в следующем примере, приведение типов, которое заканчивается с ошибкой во время выполнения, вызывает <xref:System.InvalidCastException>.  
  
 [!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 C\# предоставляет операторы [is](../../../csharp/language-reference/keywords/is.md) и [as](../../../csharp/language-reference/keywords/as.md), чтобы можно было проверить совместимость перед действительным выполнением приведения.  Дополнительные сведения см. в разделе [Практическое руководство. Безопасное приведение с помощью операторов as и is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Важная глава книги  
 [Дополнительные сведения о переменных](http://go.microsoft.com/fwlink/?LinkId=221230) IN [Начало Visual c\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [Оператор \(\)](../../../csharp/language-reference/operators/invocation-operator.md)   
 [явные](../../../csharp/language-reference/keywords/explicit.md)   
 [неявные](../../../csharp/language-reference/keywords/implicit.md)   
 [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)   
 [Generalized Type Conversion](../Topic/Generalized%20Type%20Conversion.md)   
 [Exported Type Conversion](http://msdn.microsoft.com/ru-ru/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)   
 [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)