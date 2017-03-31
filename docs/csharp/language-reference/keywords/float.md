---
title: "float (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1c3a66e4f9c690effb35e280e00e29930ec64d75
ms.lasthandoff: 03/13/2017

---
# <a name="float-c-reference"></a>float (Справочник по C#)
Ключевое слово `float` обозначает простой тип, в котором хранятся 32-разрядные значения с плавающей запятой. В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `float`.  
  
|Тип|Приблизительный диапазон значений|Точность|Тип платформы .NET Framework|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|От -3.4 × 10<sup>38</sup>до +3.4 × 10<sup>38</sup>|7 знака|<xref:System.Single?displayProperty=fullName>|  
  
## <a name="literals"></a>Литералы  
 По умолчанию фактический числовой литерал в правой части оператора назначения обрабатывается как [double](double.md). Таким образом, для инициализации переменной с плавающей запятой следует использовать суффикс `f` или `F`, как показано в следующих примерах:  
  
```csharp
float x = 3.5F;  
```
  
 Если этот суффикс не указан в предыдущем объявлении, вы получите ошибку компиляции, поскольку пытаетесь сохранить значение [double](double.md) в переменную `float`.  
  
## <a name="conversions"></a>Преобразования  
 В одном и том же выражении можно сочетать и числовые целочисленные типы и типы с плавающей запятой. В этом случае целочисленные типы преобразуются в типы с плавающей запятой. Выражение вычисляется по следующим правилам:  
  
-   Если одним из типов с плавающей запятой является [double](double.md), то выражение оценивается в реляционных или логических выражениях как [double](double.md) или [bool](bool.md).  
  
-   Если в выражении нет типа [double](double.md), выражение оценивается в реляционных или логических выражениях как `float` или [bool](bool.md).  
  
 Выражение с плавающей запятой может содержать следующие наборы значений:  
  
-   Положительный и отрицательный ноль  
  
-   Положительная и отрицательная бесконечность  
  
-   Нечисловое значение (NaN)  
  
-   Конечный набор ненулевых значений  
  
 Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269).  
  
## <a name="example"></a>Пример  
 В следующем примере [int](int.md), [short](short.md) и `float` включены в математическое выражение и дают результат `float`. (Помните, что `float` является псевдонимом для типа <xref:System.Single?displayProperty=fullName>.) Обратите внимание, что в выражении нет типа [double](double.md).  
  
 [!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Single>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [Ключевые слова в C#](index.md)   
 [Таблица целых типов](integral-types-table.md)   
 [Таблица встроенных типов](built-in-types-table.md)   
 [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md)   
 [Таблица явных числовых преобразований](explicit-numeric-conversions-table.md)
