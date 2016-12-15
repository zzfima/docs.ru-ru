---
title: "double (справочник по C#) | Microsoft Docs"
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
  - "double"
  - "double_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "double - тип данных [C#]"
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# double (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `double` обозначает простой тип, используемый для хранения 64\-разрядных значений с плавающей запятой.  В следующей таблице представлен приблизительный диапазон и точность для типа `double`.  
  
|Тип|Приблизительный диапазон|Точность|Тип платформы .NET Framework|  
|---------|------------------------------|--------------|----------------------------------|  
|`double`|от ±5,0 Ч 10<sup>−324</sup> до ±1,7 Ч 10<sup>308</sup>|15\-16 знаков|<xref:System.Double?displayProperty=fullName>|  
  
## Литералы  
 По умолчанию фактический численный литерал в правой части оператора назначения обрабатывается как тип `double`.  При этом, если необходимо, чтобы целое число обрабатывалось как тип `double`, следует использовать суффикс d или D, например:  
  
```  
  
double x = 3D;  
```  
  
## Преобразования  
 В одном выражении можно вместе использовать целочисленные типы и типы с плавающей запятой.  В таком случае целочисленные типы преобразуются в типы с плавающей запятой.  Вычисление выражения выполняется в соответствии со следующими правилами.  
  
-   Если одним из типов с плавающей запятой является `double`, результатом вычисления выражения является тип `double` или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных либо логических выражениях.  
  
-   Если в выражении не используется тип `double`, результатом вычисления является тип [float](../../../csharp/language-reference/keywords/float.md) или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных либо логических выражениях.  
  
 Выражения с плавающей запятой могут содержать следующие наборы значений:  
  
-   положительный и отрицательный ноль;  
  
-   положительную и отрицательную бесконечность;  
  
-   нечисловое значение \(NaN\);  
  
-   конечный набор ненулевых значений;  
  
 Дополнительные сведения об этих значениях см. в документе "Стандарт организации IEEE в отношении двоичной арифметики с плавающей запятой" \(IEEE Standard Binary Floating\-Point Arithmetic\), который доступен на веб\-узле организации [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) \(на английском языке\).  
  
## Пример  
 В следующим примере складываются значения, имеющие типы [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) и `double`. При этом получается результат, имеющий тип `double`.  
  
 [!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Таблица типов с плавающей запятой](../../../csharp/language-reference/keywords/floating-point-types-table.md)   
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)