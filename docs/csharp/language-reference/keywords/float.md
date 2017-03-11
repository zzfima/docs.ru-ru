---
title: "float (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "float"
  - "float_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "float - ключевое слово [C#]"
  - "числа с плавающей запятой [C#], float - ключевое слово"
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# float (Справочник по C#)
Ключевое слово `float` обозначает простой тип, используемый для хранения 32\-разрядных значений с плавающей запятой.  В следующей таблице представлен приблизительный диапазон и точность для типа `float`.  
  
|Тип|Приблизительный диапазон|Точность|Тип платформы .NET Framework|  
|---------|------------------------------|--------------|----------------------------------|  
|`float`|\-3.4 × 10<sup>38</sup>to \+3.4 × 10<sup>38</sup>|7 знаков|<xref:System.Single?displayProperty=fullName>|  
  
## Литералы  
 По умолчанию фактический численный литерал в правой части оператора назначения обрабатывается как тип [double](../../../csharp/language-reference/keywords/double.md).  Следовательно, для инициализации переменной типа с плавающей запятой нужно использовать суффикс `f` или `F`, как показано в следующем примере:  
  
```  
  
float x = 3.5F;  
```  
  
 Если в предыдущем объявлении не использовать суффикс, то будет выдана ошибка компиляции, потому что это приведет к попытке сохранить значение типа [double](../../../csharp/language-reference/keywords/double.md) в переменной типа `float`.  
  
## Преобразования  
 В одном выражении можно вместе использовать целочисленные типы и типы с плавающей запятой.  В таком случае целочисленные типы преобразуются в типы с плавающей запятой.  Вычисление выражения выполняется в соответствии со следующими правилами.  
  
-   Если одним из типов с плавающей запятой является [double](../../../csharp/language-reference/keywords/double.md), то результатом вычисления выражения является тип [double](../../../csharp/language-reference/keywords/double.md) или [bool](../../../csharp/language-reference/keywords/bool.md) в случае выражений сравнения либо логических выражений.  
  
-   Если в выражении не используется тип [double](../../../csharp/language-reference/keywords/double.md), то результатом вычисления выражения является тип `float` или [bool](../../../csharp/language-reference/keywords/bool.md) в случае выражений сравнения либо логических выражений.  
  
 Выражения с плавающей запятой могут содержать следующие наборы значений:  
  
-   положительный и отрицательный ноль;  
  
-   положительную и отрицательную бесконечность;  
  
-   нечисловое значение \(NaN\);  
  
-   Конечный набор ненулевых значений.  
  
 Дополнительные сведения об этих значениях см. в документе "Стандарт организации IEEE в отношении двоичной арифметики с плавающей запятой" \(IEEE Standard Binary Floating\-Point Arithmetic\), который доступен на веб\-узле организации [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) \(на английском языке\).  
  
## Пример  
 В следующем примере типы [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md) и `float` включены в математическое выражение, результатом вычисления которого является тип `float`.  \(Следует помнить, что ключевое слово `float` является псевдонимом типа <xref:System.Single?displayProperty=fullName>\). Обратите внимание, что тип [double](../../../csharp/language-reference/keywords/double.md) в этом выражении отсутствует.  
  
 [!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/csharp/float_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Single>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)