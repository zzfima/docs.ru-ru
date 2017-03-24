---
title: "Оператор =&gt; (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "=>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "лямбда-оператор [C#]"
  - "=> - оператор [C#]"
  - "лямбда-выражения [C#], оператор =>"
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Оператор =&gt; (Справочник по C#)
Маркер `=>` называется лямбда\-оператором.  Он используется в *лямбда\-выражениях* для отделения входных переменных с левой стороны от тела лямбда\-выражения с правой стороны.  Лямбда\-выражения — это встроенные выражения, аналогичные анонимным методам, но более гибкие. Они широко используются в запросах LINQ, выраженных с использованием синтаксиса методов.  Дополнительные сведения см. в разделе [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 В следующем примере показано два способа найти 2 и отображения длина наиболее короткой строк в массиве строк.  В первой части примера лямбда\-выражение применяется \(`w => w.Length`\) к каждому элементу массива `words` и затем используется метод <xref:System.Linq.Enumerable.Min%2A> для поиска является наименьшей длина.  Для сравнения вторая часть выводу более полное решение, использующее задачи синтаксиса запросов, то же действие.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## Заметки  
 Оператор `=>` имеет тот же приоритет, что и оператор присваивания \(`=`\) и является правоассоциативным.  
  
 Можно определить тип входной переменной значения явно или позволить компилятору передавать его; в любом случае переменная строго типизированным во время компиляции.  При определении типа необходимо заключить имя типа и имя переменной в скобки, как показано в следующем примере.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Пример  
 В следующем примере показано, как создать лямбда\-выражение перегруженной функции <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> для стандартных операторов запросов, которая принимает 2 аргумента.  Поскольку лямбда\-выражение имеет несколько параметров, параметры должны быть заключены в скобки.  Второй параметр, `index`, представляет собой индекс текущего элемента в коллекции.  Выражение `Where` возвращает все строки, длина которых их позиции индекса в массиве.  
  
```c#  
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
  
    // Compare the following code, which arrives at the same list of short  
    // digits but takes more work to get there.  
    Console.WriteLine("\nExample that uses a for loop:");  
    List<string> shortDigits2 = new List<string>();  
    for (var i = 0; i < digits.Length; i++)  
    {  
        if (digits[i].Length < i)  
            shortDigits2.Add(digits[i]);  
    }  
  
    foreach (var d in shortDigits2)  
    {  
        Console.WriteLine(d);  
    }  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
  
    // Example that uses a for loop:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)