---
title: "Checked и Unchecked (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
