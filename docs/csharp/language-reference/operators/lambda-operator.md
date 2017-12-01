---
title: "Оператор =&gt; (справочник по C#)"
ms.date: 10/02/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44cb0485aefa8b0ab10a00ae0525180020ce436d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="gt-operator-c-reference"></a>Оператор =&gt; (справочник по C#)

`=>` Оператор можно использовать двумя способами, в C#:

- Как [лямбда-оператора](#lamba-operator) в [лямбда-выражение](../../lambda-expressions.md), он позволяет разграничить входные переменные из тела лямбда-выражения.
 
- В [Определение текста выражения](#expression-body-definition), имя члена, отделяются от реализации элемента. 

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
## <a name="expression-body-definition"></a>Определение текста выражения

Определение текста выражения предоставляет реализацию участника в форме высокой краткие, доступные для чтения. Он имеет следующий общий синтаксис:

```csharp
member => expression;
```
здесь *expression* является допустимым выражением. Обратите внимание, что *выражение* может быть *выражения оператора* только если элемент возвращаемого типа `void`, или если элемент является конструктор или метод завершения.

Определения текста выражений для методов и операторов get свойства поддерживаются начиная с C# 6. Определения текста выражений для конструкторы, методы завершения, инструкции set свойства и индексаторы поддерживаются начиная с C# 7.

Ниже приводится определение тело выражения для `Person.ToString` метод:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Это сокращенная версия следующие определения метода:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
Более подробные сведения для определения текста выражений см. в разделе [выражение телом члены](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="see-also"></a>См. также  
[Справочник по C#](../../../csharp/language-reference/index.md)   
[Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
[Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[Выражение телом члены](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).