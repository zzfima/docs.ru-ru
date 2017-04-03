---
title: "Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7843620518dd7965724f0108a8fa008c95bd4793
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#)
Вы можете расширить набор методов, которые можно использовать для запросов LINQ путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>. Например, помимо стандартных операций вычисления среднего или максимального значения, можно создать настраиваемый метод агрегирования для вычисления одного значения на основе последовательности значений. Также можно создать метод, который работает как настраиваемый фильтр или особое преобразование данных для последовательности значений и возвращает новую последовательность. Примерами таких методов являются <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> и <xref:System.Linq.Enumerable.Reverse%2A>.  
  
 При расширении интерфейса <xref:System.Collections.Generic.IEnumerable%601> настраиваемые методы можно применять к любой перечислимой коллекции. Дополнительные сведения см. в разделе [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## <a name="adding-an-aggregate-method"></a>Использование метода агрегирования  
 Метод агрегирования вычисляет одно значение на основе набора значений. LINQ предоставляет несколько методов агрегирования, включая <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> и <xref:System.Linq.Enumerable.Max%2A>. Вы можете создать собственный метод агрегирования, добавив метод расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.  
  
 В следующем примере кода показано, как создать метод расширения `Median` для вычисления срединного значения последовательности чисел типа `double`.  
  
```cs  
public static class LINQExtension  
{  
    public static double Median(this IEnumerable<double> source)  
    {  
        if (source.Count() == 0)  
        {  
            throw new InvalidOperationException("Cannot compute median for an empty set.");  
        }  
  
        var sortedList = from number in source  
                         orderby number  
                         select number;  
  
        int itemIndex = (int)sortedList.Count() / 2;  
  
        if (sortedList.Count() % 2 == 0)  
        {  
            // Even number of items.  
            return (sortedList.ElementAt(itemIndex) + sortedList.ElementAt(itemIndex - 1)) / 2;  
        }  
        else  
        {  
            // Odd number of items.  
            return sortedList.ElementAt(itemIndex);  
        }  
    }  
}  
```  
  
 Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы агрегирования из интерфейса <xref:System.Collections.Generic.IEnumerable%601>.  
  
 В следующем примере кода показано использование метода `Median` для массива типа `double`.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Перегрузка метода агрегирования для принятия различных типов  
 Метод агрегирования можно перегрузить, чтобы он принимал последовательности различных типов. Стандартный способ — создание перегрузки для каждого типа. Другой подход заключается в создании перегрузки, которая будет принимать универсальный тип и преобразовывать его в конкретный тип с помощью делегата. Вы можете сочетать оба способа.  
  
#### <a name="to-create-an-overload-for-each-type"></a>Создание перегрузки для каждого типа  
 Вы можете создать конкретную перегрузку для каждого типа, который требуется поддерживать. В следующем примере кода показана перегрузка метода `Median` для типа `integer`.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Теперь можно вызвать перегрузки `Median` для типов `integer` и `double`, как показано в следующем примере кода:  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
#### <a name="to-create-a-generic-overload"></a>Создание универсальной перегрузки  
 Вы также можете создать перегрузку, которая принимает последовательность универсальных объектов. Эта перегрузка принимает делегат в качестве параметра и использует его для преобразования последовательности объектов универсального типа в конкретный тип.  
  
 В следующем примере кода демонстрируется перегрузка метода `Median`, принимающая делегат <xref:System.Func%602> в качестве параметра. Этот делегат принимает объект универсального типа T и возвращает объект типа `double`.  
  
```cs  
// Generic overload.  
  
public static double Median<T>(this IEnumerable<T> numbers,  
                       Func<T, double> selector)  
{  
    return (from num in numbers select selector(num)).Median();  
}  
```  
  
 Теперь вы можете вызвать метод `Median` для последовательности объектов любого типа. Если тип не содержит собственную перегрузку метода, вам потребуется передать параметр делегата. В C# для этой цели можно использовать лямбда-выражение. Кроме того, только в Visual Basic, если вы используете предложение `Aggregate` или `Group By` вместо вызова метода, вы можете передать любое значение или выражение, которое находится в области этого предложения.  
  
 В следующем примере кода показано, как вызвать метод `Median` для массива целых чисел и массива строк. Для строк вычисляется срединное значение длин строк в массиве. В примере демонстрируется передача параметра делегата <xref:System.Func%602> в метод `Median` для каждого из случаев.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
## <a name="adding-a-method-that-returns-a-collection"></a>Добавление метода, возвращающего коллекцию  
 Вы можете расширить интерфейс <xref:System.Collections.Generic.IEnumerable%601> с помощью метода настраиваемого запроса, который возвращает последовательность значений. В этом случае метод должен возвращать коллекцию типа <xref:System.Collections.Generic.IEnumerable%601>. Такие методы можно использовать для применения фильтров или преобразований данных к последовательности значений.  
  
 В следующем примере показано, как создать метод расширения с именем `AlternateElements`, который возвращает каждый второй элемент в коллекции, начиная с первого элемента.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 Этот метод расширения вызывается для любых перечислимых коллекций так же, как другие методы из интерфейса <xref:System.Collections.Generic.IEnumerable%601>, как показано в следующем примере кода:  
  
```cs  
string[] strings = { "a", "b", "c", "d", "e" };  
  
var query = strings.AlternateElements();  
  
foreach (var element in query)  
{  
    Console.WriteLine(element);  
}  
/*  
 This code produces the following output:  
  
 a  
 c  
 e  
*/  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic.IEnumerable%601>   
 [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
