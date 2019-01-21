---
title: Оператор =&gt;. Справочник по C#
ms.custom: seodec18
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 8641757d9252c88cf30595cec06d27b964e4d95c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415290"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="20545-102">Оператор =&gt; (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="20545-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="20545-103">Оператор `=>` можно использовать в C# двумя способами:</span><span class="sxs-lookup"><span data-stu-id="20545-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="20545-104">Как [лямбда-оператор](#lambda-operator) в [лямбда-выражении](../../lambda-expressions.md) он разграничивает входные переменные из тела лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="20545-104">As the [lambda operator](#lambda-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="20545-105">В [определении тела выражения](#expression-body-definition) он разграничивает имя члена и реализацию члена.</span><span class="sxs-lookup"><span data-stu-id="20545-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="20545-106">Лямбда-оператор</span><span class="sxs-lookup"><span data-stu-id="20545-106">Lambda operator</span></span>

<span data-ttu-id="20545-107">Маркер `=>` называется лямбда-оператором.</span><span class="sxs-lookup"><span data-stu-id="20545-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="20545-108">Он используется в *лямбда-выражениях* для отделения входных переменных с левой стороны от тела лямбда-выражения с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="20545-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="20545-109">Лямбда-выражения — это встроенные выражения, аналогичные анонимным методам, но более гибкие. Они широко используются в запросах LINQ, выраженных с использованием синтаксиса методов.</span><span class="sxs-lookup"><span data-stu-id="20545-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="20545-110">Дополнительные сведения см. в разделе [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="20545-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="20545-111">В следующем примере показано два способа поиска и отображения длины самой короткой строки в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="20545-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="20545-112">В первой части примера лямбда-выражение (`w => w.Length`) применяется к каждому элементу массива `words`, а затем используется метод <xref:System.Linq.Enumerable.Min%2A> для поиска наименьшей длины.</span><span class="sxs-lookup"><span data-stu-id="20545-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="20545-113">Для сравнения — вторая часть примера показывает более долгое решение, использующее синтаксис запросов для выполнения того же действия.</span><span class="sxs-lookup"><span data-stu-id="20545-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
### <a name="remarks"></a><span data-ttu-id="20545-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="20545-114">Remarks</span></span>  
 <span data-ttu-id="20545-115">Оператор `=>` имеет тот же приоритет, что и оператор присваивания (`=`) и является правоассоциативным.</span><span class="sxs-lookup"><span data-stu-id="20545-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="20545-116">Можно явно задать тип входной переменной или позволить компилятору передать его. В любом случае переменная является строго типизированной во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="20545-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="20545-117">При указании типа необходимо заключить имя типа и имя переменной в скобки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="20545-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="20545-118">Пример</span><span class="sxs-lookup"><span data-stu-id="20545-118">Example</span></span>  
 <span data-ttu-id="20545-119">В следующем примере показано, как создать лямбда-выражение для перегрузки стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>, который принимает два аргумента.</span><span class="sxs-lookup"><span data-stu-id="20545-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="20545-120">Поскольку лямбда-выражение имеет несколько параметров, параметры должны заключаться в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="20545-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="20545-121">Второй параметр `index` представляет собой индекс текущего элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="20545-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="20545-122">Выражение `Where` возвращает все строки, длина которых меньше индекса их позиции в массиве.</span><span class="sxs-lookup"><span data-stu-id="20545-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
## <a name="expression-body-definition"></a><span data-ttu-id="20545-123">Определения тела выражения</span><span class="sxs-lookup"><span data-stu-id="20545-123">Expression body definition</span></span>

<span data-ttu-id="20545-124">Определения тела выражения позволяют предоставлять реализацию элемента самым понятным способом.</span><span class="sxs-lookup"><span data-stu-id="20545-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="20545-125">Они имеют следующий общий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="20545-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="20545-126">здесь *expression* является допустимым выражением.</span><span class="sxs-lookup"><span data-stu-id="20545-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="20545-127">Обратите внимание, что *выражение* может быть *выражением оператора* только в том случае, если для элемента возвращается значение типа `void` или элемент является конструктором или методом завершения.</span><span class="sxs-lookup"><span data-stu-id="20545-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="20545-128">Определения тела выражения для методов и операторов property get поддерживаются начиная с C# 6.</span><span class="sxs-lookup"><span data-stu-id="20545-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="20545-129">Определения тела выражения для конструкторов, методов завершения, операторов property set и индексаторов поддерживаются начиная с C# 7.</span><span class="sxs-lookup"><span data-stu-id="20545-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="20545-130">Ниже приводится определение тела выражения для метода `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="20545-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="20545-131">Это сокращенная версия следующего определения метода:</span><span class="sxs-lookup"><span data-stu-id="20545-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="20545-132">Дополнительную информацию об определениях тела выражения см. в разделе [Элементы, воплощающие выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="20545-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="20545-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20545-133">See Also</span></span>

- [<span data-ttu-id="20545-134">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="20545-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)   
- [<span data-ttu-id="20545-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="20545-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)   
- [<span data-ttu-id="20545-136">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="20545-136">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
- <span data-ttu-id="20545-137">[Элементы, воплощающие выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="20545-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>
