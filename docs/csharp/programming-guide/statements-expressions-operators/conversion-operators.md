---
title: "Операторы преобразования (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c12fd13d6526d79363f973ce2a944c4823bf4104
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="conversion-operators-c-programming-guide"></a>Операторы преобразования (Руководство по программированию в C#)
Разработчики на C# могут объявлять преобразования классов или структур в другие классы, структуры или базовые типы и обратно. Преобразования определяются как операторы и называются по имени типа, в который осуществляется преобразование. В качестве содержащего типа должен выступать либо тип преобразуемого аргумента, либо тип результата преобразования, но не оба эти типа.  
  
 [!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
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
 [Связанные пользовательские явные преобразования в C#](http://go.microsoft.com/fwlink/?LinkId=112384)

