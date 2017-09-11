---
title: "Практическое руководство: запрос к предложениям, содержащим указанный набор слов (LINQ) (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: a5ae8ced-61fe-4c10-bb8a-95630e50f603
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6da15fca0044c1b519d9de9e3785977cda344f06
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-visual-basic"></a><span data-ttu-id="51a90-102">Практическое руководство. Запрос к предложениям, содержащим указанный набор слов (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51a90-102">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="51a90-103">В этом примере показано, как поиск предложений в текстовом файле, содержащих совпадения для каждого из указанного набора слов.</span><span class="sxs-lookup"><span data-stu-id="51a90-103">This example shows how to find sentences in a text file that contain matches for each of a specified set of words.</span></span> <span data-ttu-id="51a90-104">Несмотря на то, что массив условия поиска жестко закодирована в этом примере, его можно заполнять динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="51a90-104">Although the array of search terms is hard-coded in this example, it could also be populated dynamically at runtime.</span></span> <span data-ttu-id="51a90-105">В этом примере запрос возвращает предложения, которые содержат слова «Всегда», «данные» и «встроенной».</span><span class="sxs-lookup"><span data-stu-id="51a90-105">In this example, the query returns the sentences that contain the words "Historically," "data," and "integrated."</span></span>  
  
## <a name="example"></a><span data-ttu-id="51a90-106">Пример</span><span class="sxs-lookup"><span data-stu-id="51a90-106">Example</span></span>  
  
```vb  
Class FindSentences  
  
    Shared Sub Main()  
        Dim text As String = "Historically, the world of data and the world of objects " &   
        "have not been well integrated. Programmers work in C# or Visual Basic " &   
        "and also in SQL or XQuery. On the one side are concepts such as classes, " &   
        "objects, fields, inheritance, and .NET Framework APIs. On the other side " &   
        "are tables, columns, rows, nodes, and separate languages for dealing with " &   
        "them. Data types often require translation between the two worlds; there are " &   
        "different standard functions. Because the object world has no notion of query, a " &   
        "query can only be represented as a string without compile-time type checking or " &   
        "IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " &   
        "objects in memory is often tedious and error-prone."  
  
        ' Split the text block into an array of sentences.  
        Dim sentences As String() = text.Split(New Char() {".", "?", "!"})  
  
        ' Define the search terms. This list could also be dynamically populated at runtime  
        Dim wordsToMatch As String() = {"Historically", "data", "integrated"}  
  
        ' Find sentences that contain all the terms in the wordsToMatch array  
        ' Note that the number of terms to match is not specified at compile time  
        Dim sentenceQuery = From sentence In sentences   
                            Let w = sentence.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                   StringSplitOptions.RemoveEmptyEntries)   
                            Where w.Distinct().Intersect(wordsToMatch).Count = wordsToMatch.Count()   
                            Select sentence  
  
        ' Execute the query  
        For Each str As String In sentenceQuery  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Class  
' Output:  
' Historically, the world of data and the world of objects have not been well integrated  
```  
  
 <span data-ttu-id="51a90-107">Запрос выполняется, сначала разделяет текст на предложения, а затем разделяет предложения на массив строк, содержащих слова.</span><span class="sxs-lookup"><span data-stu-id="51a90-107">The query works by first splitting the text into sentences, and then splitting the sentences into an array of strings that hold each word.</span></span> <span data-ttu-id="51a90-108">Для каждого из этих массивов <xref:System.Linq.Enumerable.Distinct%2A>метод удаляет все повторяющиеся слова, а затем выполняет запрос <xref:System.Linq.Enumerable.Intersect%2A>операции в массиве слов и `wordsToMatch` массива.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Distinct%2A></span><span class="sxs-lookup"><span data-stu-id="51a90-108">For each of these arrays, the <xref:System.Linq.Enumerable.Distinct%2A> method removes all duplicate words, and then the query performs an <xref:System.Linq.Enumerable.Intersect%2A> operation on the word array and the `wordsToMatch` array.</span></span> <span data-ttu-id="51a90-109">Если число пересечений совпадает число `wordsToMatch` массива, все слова были найдены и возвращается исходное предложение.</span><span class="sxs-lookup"><span data-stu-id="51a90-109">If the count of the intersection is the same as the count of the `wordsToMatch` array, all words were found in the words and the original sentence is returned.</span></span>  
  
 <span data-ttu-id="51a90-110">При вызове <xref:System.String.Split%2A>, знаки пунктуации используются как разделители, чтобы удалить их из строки.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="51a90-110">In the call to <xref:System.String.Split%2A>, the punctuation marks are used as separators in order to remove them from the string.</span></span> <span data-ttu-id="51a90-111">Если было не это, например, имеется строка «Исторически», которая не будет совпадать в «Исторически» `wordsToMatch` массива.</span><span class="sxs-lookup"><span data-stu-id="51a90-111">If you did not do this, for example you could have a string "Historically," that would not match "Historically" in the `wordsToMatch` array.</span></span> <span data-ttu-id="51a90-112">Может потребоваться использовать дополнительные разделители, в зависимости от типов препинания в исходном тексте.</span><span class="sxs-lookup"><span data-stu-id="51a90-112">You may have to use additional separators, depending on the types of punctuation found in the source text.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="51a90-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="51a90-113">Compiling the Code</span></span>  
 <span data-ttu-id="51a90-114">Создайте проект, в платформе .NET Framework версии 3.5 или более поздней версии с ссылку на библиотеку System.Core.dll и `Imports` оператор для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="51a90-114">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a90-115">См. также</span><span class="sxs-lookup"><span data-stu-id="51a90-115">See Also</span></span>  
 [<span data-ttu-id="51a90-116">LINQ и строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51a90-116">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
