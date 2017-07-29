---
title: "Пример отложенного выполнения (C#)"
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
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fdbe45ceda1c7c1d82664bcf3b84b79b4fd85511
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="deferred-execution-example-c"></a>Пример отложенного выполнения (C#)
В данном разделе показано влияние отложенного выполнения и отложенного вычисления на запросы LINQ to XML.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется порядок выполнения при использовании метода расширения, в котором применяется отложенное выполнение. В этом примере объявляется массив из трех строк. Затем в нем производится итерация по коллекции, возвращенной `ConvertCollectionToUpperCase`.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 Обратите внимание, что во время итерации по коллекции, возвращенной `ConvertCollectionToUpperCase`, происходит получение каждого элемента из исходного массива строк и преобразование символов в верхний регистр до получения следующего элемента из исходного массива строк.  
  
 Видно, что весь массив строк не преобразуется в символы верхнего регистра, пока каждый элемент возвращенной коллекции не будет обработан циклом `foreach` в `Main`.  
  
 Следующий раздел учебника иллюстрирует объединение запросов в цепочки:  
  
-   [Пример связывания запросов (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a>См. также  
 [Учебник. Объединение запросов в цепочки (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)

