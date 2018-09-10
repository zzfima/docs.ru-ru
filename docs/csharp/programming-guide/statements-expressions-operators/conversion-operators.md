---
title: Операторы преобразования (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: cbf6a83d43a1b3a69e82a35d5d0875f62422cd3f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44183318"
---
# <a name="conversion-operators-c-programming-guide"></a>Операторы преобразования (Руководство по программированию в C#)
Разработчики на C# могут объявлять преобразования классов или структур в другие классы, структуры или базовые типы и обратно. Преобразования определяются как операторы и называются по имени типа, в который осуществляется преобразование. В качестве содержащего типа должен выступать либо тип преобразуемого аргумента, либо тип результата преобразования, но не оба эти типа.  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a>Обзор операторов преобразования  
 Операторы преобразования имеют следующие свойства:  
  
-   Преобразования, объявленные как `implicit`, выполняются автоматически при необходимости.  
  
-   Преобразования, объявленные как `explicit`, требуют вызова приведения.  
  
-   Все преобразования должны объявляться как `static`.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [explicit](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [implicit](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [static](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.Convert>  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Связанные пользовательские явные преобразования в C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
