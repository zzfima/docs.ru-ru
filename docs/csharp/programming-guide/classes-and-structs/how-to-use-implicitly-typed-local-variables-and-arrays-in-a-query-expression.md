---
title: Как выполнить Руководство по программированию на C#. Использование явно введенных локальных переменных и массивов в выражении запроса
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: 8e3534abf961ba7b8a41eed592455962e5b551e7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979038"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Использование явно введенных локальных переменных и массивов в выражении запроса.
Неявно типизированные локальные переменные можно использовать в тех случаях, когда требуется, чтобы компилятор определял тип локальной переменной. Неявно типизированные локальные переменные необходимо использовать для хранения анонимных типов, которые часто используются в выражениях запроса. В следующих примерах демонстрируется обязательное и необязательное использование неявно типизированных локальных переменных в запросах.  
  
 Неявно типизированные локальные переменные объявляются с помощью контекстного ключевого слова [var](../../../csharp/language-reference/keywords/var.md). Дополнительные сведения см. в разделах [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) и [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показан общий сценарий, в котором использование ключевого слова `var` является обязательным: выражение запроса, создающее последовательность анонимных типов. В этом случае переменная запроса и переменная итерации в операторе `foreach` должны быть неявно типизированы с помощью ключевого слова `var`, поскольку доступ к имени анонимного типа отсутствует. Дополнительные сведения об анонимных типах см. в разделе [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a>Пример  
 В следующем примере ключевое слово `var` используется в схожей ситуации, однако при этом ключевое слово `var` является необязательным. Поскольку `student.LastName` является строкой, при выполнении запроса возвращается последовательность строк. Таким образом, `queryID` можно объявить как `System.Collections.Generic.IEnumerable<string>` вместо `var`. Ключевое слово `var` используется для удобства. В этом примере переменная итерации в операторе `foreach` явно типизируется как строка, но вместо этого может быть объявлена с помощью ключевого слова `var`. Так как тип переменной итерации не является анонимным, использование ключевого слова `var` возможно, но не обязательно. Обратите внимание, что само по себе ключевое слово `var` является не типом, а инструкцией, предписывающей компилятору определение и присвоение типа.  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Встроенный язык запросов LINQ](../../../csharp/linq/index.md)
- [var](../../../csharp/language-reference/keywords/var.md)
- [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
