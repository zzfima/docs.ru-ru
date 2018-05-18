---
title: Checked и Unchecked (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 26ea8a7864d93b8d64661db2b0dc1df6634f989a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="checked-and-unchecked-c-reference"></a>Checked и Unchecked (Справочник по C#)
Строка кода C# может выполняться как в проверенном, так и в непроверенном контексте. В проверенном контексте арифметическое переполнение создает исключение. В непроверенном контексте арифметическое переполнение игнорируется, а результат усекается.  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md). Укажите проверенный контекст.  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md). Укажите непроверенный контекст.  
  
 Если не выбран ни `checked`, ни `unchecked` контекст, используется контекст по умолчанию, который зависит от таких внешних факторов, как параметры компилятора.  
  
 Следующие операции не затрагиваются проверкой переполнения.  
  
-   Выражения, использующие следующие предопределенные операторы на целочисленных типах:  
  
     `++` `--` - (унарный)   `+` -   `*` `/`  
  
-   Явные числовые преобразования между целочисленными типами.  
  
 Параметр компилятора [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) позволяет указать проверенный или непроверенный контекст для всех целочисленных арифметических выражений, которые явно попадают в область действия ключевого слова `checked` или `unchecked`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md)
