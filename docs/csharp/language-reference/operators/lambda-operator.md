---
title: "Оператор =&gt; (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
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
ms.openlocfilehash: 45d4753724ed094408e8cbc5353998a67071b0e4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a>Оператор =&gt; (справочник по C#)
Маркер `=>` называется лямбда-оператором. Он используется в *лямбда-выражениях* для отделения входных переменных с левой стороны от тела лямбда-выражения с правой стороны. Лямбда-выражения — это встроенные выражения, аналогичные анонимным методам, но более гибкие. Они широко используются в запросах LINQ, выраженных с использованием синтаксиса методов. Дополнительные сведения см. в разделе [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 В следующем примере показано два способа поиска и отображения длины самой короткой строки в массиве строк. В первой части примера лямбда-выражение (`w => w.Length`) применяется к каждому элементу массива `words`, а затем используется метод <xref:System.Linq.Enumerable.Min%2A> для поиска наименьшей длины. Для сравнения — вторая часть примера показывает более долгое решение, использующее синтаксис запросов для выполнения того же действия.  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор `=>` имеет тот же приоритет, что и оператор присваивания (`=`) и является правоассоциативным.  
  
 Можно явно задать тип входной переменной или позволить компилятору передать его. В любом случае переменная является строго типизированной во время компиляции. При указании типа необходимо заключить имя типа и имя переменной в скобки, как показано в следующем примере.  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать лямбда-выражение для перегрузки стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>, который принимает два аргумента. Поскольку лямбда-выражение имеет несколько параметров, параметры должны заключаться в круглые скобки. Второй параметр `index` представляет собой индекс текущего элемента в коллекции. Выражение `Where` возвращает все строки, длина которых меньше индекса их позиции в массиве.  
  
```csharp  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

