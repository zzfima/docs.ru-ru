---
title: "double (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords: double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 232dd97e152f943137604074f24b5de779168e59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="double-c-reference"></a>double (справочник по C#)
Ключевое слово `double` обозначает простой тип, используемый для хранения 64-разрядных значений с плавающей запятой. В приведенной ниже таблице представлен точный и приблизительный диапазон значений для типа `double`.  
  
|Тип|Приблизительный диапазон значений|Точность|Тип платформы .NET Framework|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|от ±5,0 × 10<sup>−324</sup> до ±1,7 × 10<sup>308</sup>|15–16 знаков|<xref:System.Double?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Литералы  
 По умолчанию фактический числовой литерал в правой части оператора назначения обрабатывается как `double`. Если необходимо, чтобы целое число обрабатывалось как `double`, следует использовать суффикс d или D, например:  
  
```  
double x = 3D;  
```  
  
## <a name="conversions"></a>Преобразования  
 В одном и том же выражении можно сочетать и числовые целочисленные типы и типы с плавающей запятой. В этом случае целочисленные типы преобразуются в типы с плавающей запятой. Выражение вычисляется по следующим правилам:  
  
-   Если одним из типов с плавающей запятой является `double`, результатом выражения является тип `double` или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных либо логических выражениях.  
  
-   Если в выражении не используется тип `double`, результатом выражения является тип [float](../../../csharp/language-reference/keywords/float.md) или [bool](../../../csharp/language-reference/keywords/bool.md) в реляционных либо логических выражениях.  
  
 Выражение с плавающей запятой может содержать следующие наборы значений:  
  
-   положительный и отрицательный нуль;  
  
-   положительная и отрицательная бесконечность;  
  
-   нечисловое значение (NaN);  
  
-   конечный набор ненулевых значений.  
  
 Дополнительные сведения об этих значениях см. в документе "Стандарт IEEE для двоичной арифметики с плавающей запятой" на веб-сайте [IEEE](http://www.ieee.org).  
  
## <a name="example"></a>Пример  
 В следующем примере складываются значения, имеющие типы [int](../../../csharp/language-reference/keywords/int.md), [short](../../../csharp/language-reference/keywords/short.md), [float](../../../csharp/language-reference/keywords/float.md) и `double`. Получается результат, имеющий тип `double`.  
  
 [!code-csharp[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Таблица типов с плавающей запятой](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
 [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
