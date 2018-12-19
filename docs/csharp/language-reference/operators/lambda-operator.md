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
ms.openlocfilehash: c193a91eaffe2e56a5df2afa8d66989981123a48
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238797"
---
# <a name="gt-operator-c-reference"></a>Оператор =&gt; (справочник по C#)

Оператор `=>` можно использовать в C# двумя способами:

- Как [лямбда-оператор](#lamba-operator) в [лямбда-выражении](../../lambda-expressions.md) он разграничивает входные переменные из тела лямбда-выражения.
 
- В [определении тела выражения](#expression-body-definition) он разграничивает имя члена и реализацию члена. 

## <a name="lambda-operator"></a>Лямбда-оператор

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
  
### <a name="remarks"></a>Примечания  
 Оператор `=>` имеет тот же приоритет, что и оператор присваивания (`=`) и является правоассоциативным.  
  
 Можно явно задать тип входной переменной или позволить компилятору передать его. В любом случае переменная является строго типизированной во время компиляции. При указании типа необходимо заключить имя типа и имя переменной в скобки, как показано в следующем примере.  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как создать лямбда-выражение для перегрузки стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>, который принимает два аргумента. Поскольку лямбда-выражение имеет несколько параметров, параметры должны заключаться в круглые скобки. Второй параметр `index` представляет собой индекс текущего элемента в коллекции. Выражение `Where` возвращает все строки, длина которых меньше индекса их позиции в массиве.  
  
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
## <a name="expression-body-definition"></a>Определения тела выражения

Определения тела выражения позволяют предоставлять реализацию элемента самым понятным способом. Они имеют следующий общий синтаксис:

```csharp
member => expression;
```
здесь *expression* является допустимым выражением. Обратите внимание, что *выражение* может быть *выражением оператора* только в том случае, если для элемента возвращается значение типа `void` или элемент является конструктором или методом завершения.

Определения тела выражения для методов и операторов property get поддерживаются начиная с C# 6. Определения тела выражения для конструкторов, методов завершения, операторов property set и индексаторов поддерживаются начиная с C# 7.

Ниже приводится определение тела выражения для метода `Person.ToString`:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Это сокращенная версия следующего определения метода:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
Дополнительную информацию об определениях тела выражения см. в разделе [Элементы, воплощающие выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)   
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
- [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
- [Элементы, воплощающие выражения](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).