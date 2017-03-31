---
title: "Промежуточная материализация (C#) | Документы Майкрософт"
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
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4807224faef5968828e16a4e1f11614e7ac6cf73
ms.lasthandoff: 03/13/2017


---
# <a name="intermediate-materialization-c"></a>Промежуточная материализация (C#)
Если не соблюдать осторожность, то в некоторых ситуациях может происходить преждевременная материализация коллекций в запросах, что приводит к радикальному изменению характера использования памяти и снижению производительности приложения. Некоторые стандартные операторы запросов материализуют свою исходную коллекцию еще до получения хотя бы одного элемента. Например, при выполнении оператора <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName> сначала происходит итерация по всей исходной коллекции, затем сортировка всех элементов и лишь после этого осуществляется возврат первого элемента. Это означает, что самой дорогостоящей операцией является получение первого элемента упорядоченной коллекции, после чего затраты ресурсов на каждый последующий элемент становятся меньше. Это вполне оправдано, поскольку функционирование данного оператора запроса не может быть организовано иначе.  
  
## <a name="example"></a>Пример  
 В этом примере внесены изменения по сравнению с предыдущим примером. Метод `AppendString` вызывает <xref:System.Linq.Enumerable.ToList%2A> до начала итерации по источнику. Это становится причиной материализации.  
  
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
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
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
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 В этом примере можно видеть, что применение вызова <xref:System.Linq.Enumerable.ToList%2A> вынуждает метод `AppendString` выполнить перечисление по всему источнику, прежде чем возвратить первый элемент. Если источник представляет собой большой массив, то в результате характер использования памяти приложением существенно изменится.  
  
 Стандартные операторы запроса можно также соединять в виде цепочки. Это показано в последнем разделе учебника.  
  
-   [Связывание стандартных операторов запросов (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a>См. также  
 [Учебник. Объединение запросов в цепочки (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
