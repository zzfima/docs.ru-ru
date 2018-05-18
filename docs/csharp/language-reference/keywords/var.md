---
title: var (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: 58c7e29840cfb536e2d1afd48b0ff2ca65b1c0c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="var-c-reference"></a>var (справочник по C#)
Начиная с Visual C# 3.0, переменные, объявленные в области действия метода, получают неявный "тип" `var`. Неявно типизированные локальные переменные является строго типизированными, как если бы вы объявили тип самостоятельно, однако его определяет компилятор. Следующие два объявления `i` функционально эквивалентны:  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Дополнительные сведения см. в разделах [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) и [Связи типов в операциях запроса LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показаны два выражения запросов. В первом выражении использование `var` разрешено, но не является обязательным, поскольку тип результата запроса может быть задан явно как `IEnumerable<string>`. Однако во втором выражении благодаря `var` результат может быть коллекцией анонимных типов, и имя этого типа доступно только для компилятора. Использование `var` делает создание нового класса для результата необязательным. Обратите внимание на то, что во втором примере переменная итерации `foreach` `item` также типизирована неявно.  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
