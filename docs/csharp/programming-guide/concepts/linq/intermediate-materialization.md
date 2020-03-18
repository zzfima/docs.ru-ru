---
title: Промежуточная материализация (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: af1eb7df7da02d8e72fc102cda4ee5f329dc7974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253161"
---
# <a name="intermediate-materialization-c"></a>Промежуточная материализация (C#)
Если не соблюдать осторожность, то в некоторых ситуациях может происходить преждевременная материализация коллекций в запросах, что приводит к радикальному изменению характера использования памяти и снижению производительности приложения. Некоторые стандартные операторы запросов материализуют свою исходную коллекцию еще до получения хотя бы одного элемента. Например, при выполнении оператора <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> вначале происходит итерация по всей исходной коллекции, затем сортировка всех элементов и лишь после этого осуществляется возврат первого элемента. Это означает, что самой дорогостоящей операцией является получение первого элемента упорядоченной коллекции, после чего затраты ресурсов на каждый последующий элемент становятся меньше. Это вполне оправдано, поскольку функционирование данного оператора запроса не может быть организовано иначе.  
  
## <a name="example"></a>Пример  
 В этом примере внесены изменения по сравнению с предыдущим примером. В методе `AppendString` осуществляется вызов <xref:System.Linq.Enumerable.ToList%2A> до начала итераций по данным источника. Это становится причиной материализации.  
  
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
  
```output  
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
  
 В этом примере можно видеть, что применение вызова <xref:System.Linq.Enumerable.ToList%2A> вынуждает метод `AppendString` сформировать перечисление по всему источнику, прежде чем возвратить первый элемент. Если источник представляет собой большой массив, то в результате характер использования памяти приложением существенно изменится.  
  
 Стандартные операторы запроса можно также соединять в виде цепочки. Это показано в последнем разделе учебника.  
  
- [Связывание стандартных операторов запросов (C#)](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a>См. также раздел

- [Учебник. Объединение запросов в цепочки (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
