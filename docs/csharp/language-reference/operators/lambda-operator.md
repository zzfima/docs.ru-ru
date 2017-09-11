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
# <a name="gt-operator-c-reference"></a><span data-ttu-id="bee24-102">Оператор =&gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bee24-102">=&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="bee24-103">Маркер `=>` называется лямбда-оператором.</span><span class="sxs-lookup"><span data-stu-id="bee24-103">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="bee24-104">Он используется в *лямбда-выражениях* для отделения входных переменных с левой стороны от тела лямбда-выражения с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="bee24-104">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="bee24-105">Лямбда-выражения — это встроенные выражения, аналогичные анонимным методам, но более гибкие. Они широко используются в запросах LINQ, выраженных с использованием синтаксиса методов.</span><span class="sxs-lookup"><span data-stu-id="bee24-105">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="bee24-106">Дополнительные сведения см. в разделе [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bee24-106">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="bee24-107">В следующем примере показано два способа поиска и отображения длины самой короткой строки в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="bee24-107">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="bee24-108">В первой части примера лямбда-выражение (`w => w.Length`) применяется к каждому элементу массива `words`, а затем используется метод <xref:System.Linq.Enumerable.Min%2A> для поиска наименьшей длины.</span><span class="sxs-lookup"><span data-stu-id="bee24-108">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="bee24-109">Для сравнения — вторая часть примера показывает более долгое решение, использующее синтаксис запросов для выполнения того же действия.</span><span class="sxs-lookup"><span data-stu-id="bee24-109">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="bee24-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bee24-110">Remarks</span></span>  
 <span data-ttu-id="bee24-111">Оператор `=>` имеет тот же приоритет, что и оператор присваивания (`=`) и является правоассоциативным.</span><span class="sxs-lookup"><span data-stu-id="bee24-111">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="bee24-112">Можно явно задать тип входной переменной или позволить компилятору передать его. В любом случае переменная является строго типизированной во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="bee24-112">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="bee24-113">При указании типа необходимо заключить имя типа и имя переменной в скобки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bee24-113">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
## <a name="example"></a><span data-ttu-id="bee24-114">Пример</span><span class="sxs-lookup"><span data-stu-id="bee24-114">Example</span></span>  
 <span data-ttu-id="bee24-115">В следующем примере показано, как создать лямбда-выражение для перегрузки стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>, который принимает два аргумента.</span><span class="sxs-lookup"><span data-stu-id="bee24-115">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> that takes two arguments.</span></span> <span data-ttu-id="bee24-116">Поскольку лямбда-выражение имеет несколько параметров, параметры должны заключаться в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="bee24-116">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="bee24-117">Второй параметр `index` представляет собой индекс текущего элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="bee24-117">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="bee24-118">Выражение `Where` возвращает все строки, длина которых меньше индекса их позиции в массиве.</span><span class="sxs-lookup"><span data-stu-id="bee24-118">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bee24-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bee24-119">See Also</span></span>  
 <span data-ttu-id="bee24-120">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bee24-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bee24-121">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bee24-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bee24-122">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="bee24-122">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

