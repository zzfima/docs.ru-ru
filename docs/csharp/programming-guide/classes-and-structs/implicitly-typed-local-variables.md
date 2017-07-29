---
title: "Неявно типизированные локальные переменные (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
caps.latest.revision: 23
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
ms.openlocfilehash: cc02c0f7ef5fbbbf3c60188426a8027f6a60fb89
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a>Неявно типизированные локальные переменные (Руководство по программированию в C#)
Локальные переменные можно объявлять без указания конкретного типа. Ключевое слово `var` указывает, что компилятор должен вывести тип переменной из выражения справа от оператора инициализации. Выведенный тип может быть встроенным, анонимным, определяемым пользователем либо типом, определяемым в библиотеке классов .NET Framework. Дополнительные сведения об инициализации массивов с `var` см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
 В приведенных ниже примерах показаны различные способы объявления локальных переменных с помощью `var`:  
  
 [!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 Важно понимать, что ключевое слово `var` не означает "variant" и не означает, что переменная является слабо типизированной или имеет позднее связывание. Он указывает только на то, что компилятор определяет и назначает наиболее подходящий тип.  
  
 Ключевое слово `var` можно использовать в следующих контекстах:  
  
-   С локальными переменными (переменными, объявленными в области метода), как показано в предыдущем примере.  
  
-   В операторе инициализации [for](../../../csharp/language-reference/keywords/for.md).  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   В операторе инициализации [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   В операторе [using](../../../csharp/language-reference/keywords/using-statement.md).  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Использование явно введенных локальных переменных и массивов в выражении запроса](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).  
  
## <a name="var-and-anonymous-types"></a>Переменная var и анонимные типы  
 Во многих случаях переменная `var` не является обязательной и предназначена только для синтаксического удобства. Тем не менее если переменная инициализируется с помощью анонимного типа и вам потребуется доступ к свойствам объекта на более позднем этапе, ее необходимо объявить как `var`. Это — распространенный сценарий в выражениях запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Дополнительные сведения см. в разделе [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 С точки зрения исходного кода анонимный тип безымянен. Таким образом, если переменная запроса инициализирована с помощью `var`, то единственный способ получить доступ к свойствам в возвращаемой последовательности объектов — это использовать `var` как тип переменной итерации в операторе `foreach`.  
  
 [!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## <a name="remarks"></a>Примечания  
 В объявлениям неявно типизированных переменных применяются следующие ограничения:  
  
-   `var` можно использовать только в том случае, если локальная переменная объявляется и инициализируется в одном и том же операторе; переменная не может инициализироваться в нулевое значение, в группу методов или в анонимную функцию.  
  
-   `var` нельзя применять к полям в области видимости класса.  
  
-   Переменные, объявленные с помощью `var`, нельзя использовать в выражении инициализации. Другими словами, это выражение является допустимым выражением `: int i = (i = 20);`, но вызывает ошибку времени компиляции: `var i = (i = 20);`  
  
-   Инициализировать сразу несколько неявно типизированных переменных в одном и том же операторе нельзя.  
  
-   Если тип с именем `var` входит в область видимости, то ключевое слово `var` разрешится в это имя типа и не будет обрабатываться как часть объявления неявно типизированной локальной переменной.  
  
 Переменную `var` можно также использовать в выражениях запросов, где точный сконструированный тип переменной запроса определить непросто. Подобная ситуация может возникнуть в операциях группировки и сортировки.  
  
 Кроме того, ключевое слово `var` может пригодиться, если конкретный тип переменной сложно набрать с клавиатуры, а также если он очевиден либо затрудняет чтение кода. Использовать `var` таким образом можно, например, с вложенными универсальными типами — подобные типы применяются в групповых операциях. В следующем запросе переменная запроса имеет тип `IEnumerable<IGrouping<string, Student>>`. Если вы и другие пользователи, которые работают с кодом, это понимаете, использовать неявный ввод для удобства и краткости кода можно без проблем.  
  
 [!code-cs[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]  
  
 При этом использование ключевого слова `var` может усложнить понимание вашего кода для других разработчиков. В связи с этим в документации по C# `var` применяется только в тех случаях, когда это необходимо.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)   
 [Практическое руководство. Использование явно введенных локальных переменных и массивов в выражении запроса](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [for](../../../csharp/language-reference/keywords/for.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Оператор using](../../../csharp/language-reference/keywords/using-statement.md)

