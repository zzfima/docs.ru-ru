---
title: Ключевое слово float (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: 98f89ba3d79f7679b69ce10fd875b3caf69c5257
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157708"
---
# <a name="float-c-reference"></a>float (Справочник по C#)

Ключевое слово `float` обозначает простой тип, в котором хранятся 32-разрядные значения с плавающей запятой. В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `float`.

|Тип|Приблизительный диапазон значений|Точность|Тип .NET|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|От ±1,5 x 10<sup>−45</sup> до ±3,4 x 10<sup>38</sup>|7 знака|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a>Литералы

По умолчанию фактический числовой литерал в правой части оператора назначения обрабатывается как [double](double.md). Таким образом, для инициализации переменной с плавающей запятой следует использовать суффикс `f` или `F`, как показано в следующих примерах:

```csharp
float x = 3.5F;
```

Если этот суффикс не указан в предыдущем объявлении, вы получите ошибку компиляции, поскольку пытаетесь сохранить значение [double](double.md) в переменную `float`.

## <a name="conversions"></a>Преобразования

В одном и том же выражении можно сочетать и числовые целочисленные типы и типы с плавающей запятой. В этом случае целочисленные типы преобразуются в типы с плавающей запятой. Выражение вычисляется по следующим правилам:

- Если одним из типов с плавающей запятой является [double](double.md), то выражение оценивается как [double](double.md) или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.

- Если в выражении нет типа [double](double.md), выражение оценивается как `float` или [bool](bool.md) в реляционных сравнениях или сравнениях на равенство.

Выражение с плавающей запятой может содержать следующие наборы значений:

- Положительный и отрицательный ноль

- Положительная и отрицательная бесконечность

- Нечисловое значение (NaN)

- Конечный набор ненулевых значений

Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](http://www.ieee.org).

## <a name="example"></a>Пример

В следующем примере [int](int.md), [short](short.md) и `float` включены в математическое выражение и дают результат `float`. (Помните, что `float` — это псевдоним для типа <xref:System.Single?displayProperty=nameWithType>.) Обратите внимание, что в выражении нет типа [double](double.md).

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- <xref:System.Single>  
- [Справочник по C#](../index.md)  
- [Руководство по программированию на C#](../../programming-guide/index.md)  
- [Приведение и преобразование типов](../../programming-guide/types/casting-and-type-conversions.md)  
- [Ключевые слова в C#](index.md)  
- [Таблица целых типов](integral-types-table.md)  
- [Таблица встроенных типов](built-in-types-table.md)  
- [Таблица неявных числовых преобразований](implicit-numeric-conversions-table.md)  
- [Таблица явных числовых преобразований](explicit-numeric-conversions-table.md)  