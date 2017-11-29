---
title: "Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 557e72342901fab8bbe66e9cc3405cb4b2d9c1e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="2816f-102">Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2816f-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="2816f-103">Другим методом итерации всех элементов массива является использование оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md), как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="2816f-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="2816f-104">Оператор `foreach` можно использовать для итерации всех элементов массива, класса коллекции .NET Framework либо любого класса или структуры, реализующих интерфейс <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="2816f-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2816f-105">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="2816f-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2816f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2816f-106">Example</span></span>  
 <span data-ttu-id="2816f-107">В этом примере показано, как напечатать аргументы командной строки с помощью оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="2816f-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2816f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2816f-108">See Also</span></span>  
 <xref:System.Array>  
 <xref:System.Collections>  
 [<span data-ttu-id="2816f-109">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="2816f-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [<span data-ttu-id="2816f-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2816f-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2816f-111">foreach, in</span><span class="sxs-lookup"><span data-stu-id="2816f-111">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="2816f-112">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="2816f-112">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="2816f-113">Практическое руководство. Отображение аргументов командной строки</span><span class="sxs-lookup"><span data-stu-id="2816f-113">How to: Display Command Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [<span data-ttu-id="2816f-114">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="2816f-114">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
