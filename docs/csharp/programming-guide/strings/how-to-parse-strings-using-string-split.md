---
title: "Практическое руководство. Анализ строк с помощью метода String.Split (руководство по программированию на языке C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "разделение строк [C#]"
  - "Split - метод [C#]"
  - "строки [C#], разделение"
  - "анализ строк"
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Практическое руководство. Анализ строк с помощью метода String.Split (руководство по программированию на языке C#)
В приведенном ниже примере кода демонстрируется возможность анализа строки с помощью метода <xref:System.String.Split%2A?displayProperty=fullName>. В качестве входных данных метод <xref:System.String.Split%2A> принимает массив символов, который определяет, какие символы разделяют нужные подстроки целевой строки.  Функция возвращает массив подстрок.  
  
 В этом примере в качестве символов\-разделителей используются пробелы, запятые, точки, двоеточия и символы табуляции, которые передаются в метод <xref:System.String.Split%2A> в виде массива.  Каждое слово в целевой строке отображается отдельно от полученного в результате массива строк.  
  
## Пример  
 [!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#16)]  
  
## Пример  
 По умолчанию метод String.Split возвращает пустые строки, если в целевой строке два символа\-разделителя следуют друг за другом.  Чтобы исключить из выходных данных все пустые строки, можно передать необязательный параметр StringSplitOptions.RemoveEmptyEntries.  
  
 Метод String.Split может принимать массив строк \(в этом случае в качестве разделителей при анализе целевой строки используются последовательности символов, а не отдельные символы\).  
  
```c#  
class TestStringSplit { static void Main() { char[] separatingChars = { "<<", "..." }; string text = "one<<two......three<four"; System.Console.WriteLine("Original text: '{0}'", text); string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries ); System.Console.WriteLine("{0} substrings in text:", words.Length); foreach (string s in words) { System.Console.WriteLine(s); } // Keep the console window open in debug mode. System.Console.WriteLine("Press any key to exit."); System.Console.ReadKey(); } } /* Output: Original text: 'one<<two......three<four' 3 words in text: one two three<four */  
  
```  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [Регулярные выражения в .NET Framework](../Topic/.NET%20Framework%20Regular%20Expressions.md)