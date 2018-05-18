---
title: float (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: edeed59da26c7007b23e1eec8c05fbd2e6d34d36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="float-c-reference"></a>float (Справочник по C#)
Ключевое слово `float` обозначает простой тип, в котором хранятся 32-разрядные значения с плавающей запятой. В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `float`.  
  
|Тип|Приблизительный диапазон значений|Точность|Тип платформы .NET Framework|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|От -3.4 × 10<sup>38</sup>до +3.4 × 10<sup>38</sup>|7 знака|<xref:System.Single?displayProperty=nameWithType>|  
  
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
  
 Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](http://www.ieee.org).  
  
## <a name="example"></a>Пример  
 В следующем примере [int](int.md), [short](short.md) и `float` включены в математическое выражение и дают результат `float`. (Помните, что `float` — это псевдоним для типа <xref:System.Single?displayProperty=nameWithType>.) Обратите внимание, что в выражении нет типа [double](double.md).  
  
 [!code-csharp[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
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
