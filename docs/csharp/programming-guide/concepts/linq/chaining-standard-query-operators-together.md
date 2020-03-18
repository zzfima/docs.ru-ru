---
title: Связывание стандартных операторов запросов (C#)
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 37df654b2bfdcc135460e5ded2ceec1eca33b35a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204208"
---
# <a name="chaining-standard-query-operators-together-c"></a>Связывание стандартных операторов запросов (C#)
Это последний раздел учебника [Объединение запросов в цепочки (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
 Стандартные операторы запросов также можно объединять в цепочки. Например, можно вставить оператор <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>, который также будет действовать как отложенный. Этот оператор не материализует промежуточные результаты.  
  
## <a name="example"></a>Пример  
 В данном примере метод <xref:System.Linq.Enumerable.Where%2A> вызывается до вызова метода `ConvertCollectionToUpperCase`. Метод <xref:System.Linq.Enumerable.Where%2A> действует практически так же, как отложенные методы, использовавшиеся в предыдущих примерах, приведенных в этом учебнике, `ConvertCollectionToUpperCase` и `AppendString`.  
  
 Отличие заключается в том, что в этом случае метод <xref:System.Linq.Enumerable.Where%2A> просматривает свою исходную коллекцию, определяет, что первый элемент не передает предикат, а затем переходит к следующему элементу, который предикат передает. После этого метод выдает второй элемент.  
  
 Однако базовый принцип остался прежним: промежуточные коллекции материализуются только в случае необходимости.  
  
 При использовании выражений запросов они преобразуются в вызовы стандартных операторов запросов, а затем применяется тот же принцип.  
  
 Во всех примерах, приведенных в этом разделе, в которых запрашиваются документы Office Open XML, используется один и тот же принцип. Отложенное выполнение и отложенное вычисление - это основополагающие принципы, которые необходимо понимать, чтобы эффективно использовать LINQ (и LINQ to XML).  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            where s.CompareTo("D") >= 0  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 В этом примере выводятся следующие данные:  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
