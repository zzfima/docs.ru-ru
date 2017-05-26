---
title: "var (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 1aaa231a807ec50b8bcb922bf0dd218ec72d24ff
ms.openlocfilehash: 90373937c309dbe4d888b7a2ec1b8b94a038e036
ms.contentlocale: ru-ru
ms.lasthandoff: 04/25/2017

---
# <a name="var-c-reference"></a>var (справочник по C#)
Начиная с Visual C# 3.0, переменные, объявленные в области действия метода, получают неявный "тип" `var`. Неявно типизированные локальные переменные является строго типизированными, как если бы вы объявили тип самостоятельно, однако его определяет компилятор. Следующие два объявления `i` функционально эквивалентны:  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Дополнительные сведения см. в разделах [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) и [Связи типов в операциях запроса LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показаны два выражения запросов. В первом выражении использование `var` разрешено, но не является обязательным, поскольку тип результата запроса может быть задан явно как `IEnumerable<string>`. Во втором выражении `var` необходимо использовать, поскольку результатом является коллекция анонимных типов, и имя этого типа доступно только для компилятора. Обратите внимание на то, что во втором примере переменная итерации `foreach` `item` также типизирована неявно.  
  
 [!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)

