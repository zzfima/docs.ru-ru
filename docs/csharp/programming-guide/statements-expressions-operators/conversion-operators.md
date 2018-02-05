---
title: "Операторы преобразования (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 056971dcd648208d77573c180df28ffdd46788c5
ms.sourcegitcommit: 22a48b64a0150a60b00b4fc4d8c62cde7f1670c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
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
 <xref:System.Convert>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Связанные пользовательские явные преобразования в C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
