---
title: "Пример связывания запросов (C#)"
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
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 70179c93c48f56614bd7c8b648f73e86ebe26ff4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="chaining-queries-example-c"></a>Пример связывания запросов (C#)
Этот пример основан на предыдущем примере и показывает, что происходит при соединении в цепочку двух запросов, использующих отложенное выполнение и отложенное вычисление.  
  
## <a name="example"></a>Пример  
 В этом примере представлен другой метод расширения, `AppendString`, который добавляет указанную строку в каждую строку исходной коллекции, а затем выдает новые строки.  
  
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
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 В этом примере видно, что каждый метод расширения работает поочередно с каждым элементом исходной коллекции.  
  
 Этот пример показывает, что даже при соединении в цепочку двух запросов, формирующих коллекции, промежуточные коллекции не материализуются. Вместо этого каждый элемент передается от одного отложенного метода к другому. Это приводит к использованию намного меньшего объема памяти, чем при подходе, который сначала принимает один массив строк, затем создает второй массив строк, преобразованных в символы верхнего регистра, и наконец создает третий массив строк, где каждая строка имеет добавленные к ней восклицательные знаки.  
  
 Следующий раздел учебника иллюстрирует промежуточную материализацию:  
  
-   [Промежуточная материализация (C#)](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)  
  
## <a name="see-also"></a>См. также  
 [Учебник. Объединение запросов в цепочки (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)

