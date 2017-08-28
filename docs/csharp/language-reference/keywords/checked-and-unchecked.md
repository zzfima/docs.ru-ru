---
title: "Checked и Unchecked (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: 17
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 744f59dbf7ee8370010ff76d4e9dde20490de403
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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

