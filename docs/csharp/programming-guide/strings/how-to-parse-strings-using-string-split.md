---
title: "Практическое руководство. Анализ строк с помощью метода String.Split (руководство по программированию на языке C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c0ef96f1cb074c32208457c192d53c69d95a102d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a>Практическое руководство. Анализ строк с помощью метода String.Split (руководство по программированию на языке C#)
В приведенном ниже примере кода демонстрируется возможность анализа строки с помощью метода <xref:System.String.Split%2A?displayProperty=fullName> . В качестве входных данных метод <xref:System.String.Split%2A> принимает массив символов, который определяет, какие символы разделяют нужные подстроки целевой строки.  Функция возвращает массив подстрок.  
  
 В этом примере в качестве символов-разделителей используются пробелы, запятые, точки, двоеточия и символы табуляции, которые передаются в метод <xref:System.String.Split%2A>в виде массива.  Каждое слово в целевой строке отображается отдельно от полученного в результате массива строк.  
  
## <a name="example"></a>Пример  
 [!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a>Пример  
 По умолчанию метод String.Split возвращает пустые строки, если в целевой строке два символа-разделителя следуют друг за другом.  Чтобы исключить из выходных данных все пустые строки, можно передать необязательный параметр StringSplitOptions.RemoveEmptyEntries.  
  
 Метод String.Split может принимать массив строк (в этом случае в качестве разделителей при анализе целевой строки используются последовательности символов, а не отдельные символы).  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        char[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312)

