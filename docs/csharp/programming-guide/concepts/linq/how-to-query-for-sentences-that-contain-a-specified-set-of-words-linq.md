---
title: Как запросить предложения с указанным набором слов (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
ms.openlocfilehash: df279f57d9965d796397cbcf7a0f3ba05bf9e5c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168860"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a>Как запросить предложения с указанным набором слов (LINQ) (C#)
В этом примере показан поиск предложений, содержащих совпадения для каждого из указанного набора слов в текстовом файле. Хотя массив терминов для поиска в этом примере жестко закодирован, его можно заполнять динамически во время выполнения. В этом примере запрос возвращает предложения, которые содержат слова "Historically", "data" и "integrated".  
  
## <a name="example"></a>Пример  
  
```csharp  
class FindSentences  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects " +  
        @"have not been well integrated. Programmers work in C# or Visual Basic " +  
        @"and also in SQL or XQuery. On the one side are concepts such as classes, " +  
        @"objects, fields, inheritance, and .NET Framework APIs. On the other side " +  
        @"are tables, columns, rows, nodes, and separate languages for dealing with " +  
        @"them. Data types often require translation between the two worlds; there are " +  
        @"different standard functions. Because the object world has no notion of query, a " +  
        @"query can only be represented as a string without compile-time type checking or " +  
        @"IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " +  
        @"objects in memory is often tedious and error-prone.";  
  
        // Split the text block into an array of sentences.  
        string[] sentences = text.Split(new char[] { '.', '?', '!' });  
  
        // Define the search terms. This list could also be dynamically populated at runtime.  
        string[] wordsToMatch = { "Historically", "data", "integrated" };  
  
        // Find sentences that contain all the terms in the wordsToMatch array.  
        // Note that the number of terms to match is not specified at compile time.  
        var sentenceQuery = from sentence in sentences  
                            let w = sentence.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' },  
                                                    StringSplitOptions.RemoveEmptyEntries)  
                            where w.Distinct().Intersect(wordsToMatch).Count() == wordsToMatch.Count()  
                            select sentence;  
  
        // Execute the query. Note that you can explicitly type  
        // the iteration variable here even though sentenceQuery  
        // was implicitly typed.
        foreach (string str in sentenceQuery)  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
Historically, the world of data and the world of objects have not been well integrated  
*/  
```  
  
 Запрос сначала разделяет текст на предложения, а затем разделяет предложения на массив строк, содержащих слова. Для каждого из этих массивов метод <xref:System.Linq.Enumerable.Distinct%2A> удаляет все повторяющиеся слова, после чего выполняет операцию <xref:System.Linq.Enumerable.Intersect%2A> в отношении массива слов и массива `wordsToMatch`. Если число пересечений совпадает с размером массива `wordsToMatch`, все слова были найдены и возвращается исходное предложение.  
  
 В вызове <xref:System.String.Split%2A> знаки пунктуации используются как разделители для того, чтобы удалить их из строки. Если этого не сделать, то, например, можно получить строку "Historically," которая не будет совпадать с "Historically" в массиве `wordsToMatch`. В зависимости от знаков препинания в исходном тексте может потребоваться использовать дополнительные разделители.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.

## <a name="see-also"></a>См. также раздел

- [LINQ и строки (C#)](./linq-and-strings.md)
