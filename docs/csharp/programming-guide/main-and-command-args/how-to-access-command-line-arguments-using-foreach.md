---
title: "Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 766b5cd0879edec1dc409e07c4f62ee693fd615d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="bc9ea-102">Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="bc9ea-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="bc9ea-103">Другим методом итерации всех элементов массива является использование оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md), как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="bc9ea-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="bc9ea-104">Оператор `foreach` можно использовать для итерации всех элементов массива, класса коллекции .NET Framework либо любого класса или структуры, реализующих интерфейс <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="bc9ea-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc9ea-105">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="bc9ea-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9ea-106">Пример</span><span class="sxs-lookup"><span data-stu-id="bc9ea-106">Example</span></span>  
 <span data-ttu-id="bc9ea-107">В этом примере показано, как напечатать аргументы командной строки с помощью оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="bc9ea-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 <span data-ttu-id="bc9ea-108">[!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc9ea-108">[!code-cs[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]</span></span>  
  
 <span data-ttu-id="bc9ea-109">[!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc9ea-109">[!code-cs[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9ea-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bc9ea-110">See Also</span></span>  
 <span data-ttu-id="bc9ea-111"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="bc9ea-111"><xref:System.Array></span></span>   
 <span data-ttu-id="bc9ea-112"><xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="bc9ea-112"><xref:System.Collections></span></span>   
 <span data-ttu-id="bc9ea-113">[Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="bc9ea-113">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="bc9ea-114">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc9ea-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bc9ea-115">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="bc9ea-115">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 <span data-ttu-id="bc9ea-116">[Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc9ea-116">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="bc9ea-117">[Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="bc9ea-117">[How to: Display Command Line Arguments](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md) </span></span>  
 [<span data-ttu-id="bc9ea-118">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="bc9ea-118">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

