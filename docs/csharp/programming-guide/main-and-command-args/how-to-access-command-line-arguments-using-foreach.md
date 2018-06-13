---
title: Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 2f1723efd4056539e12605bc1a4229f94bc9e055
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332511"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="af6f8-102">Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="af6f8-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="af6f8-103">Другим методом итерации всех элементов массива является использование оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md), как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="af6f8-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="af6f8-104">Оператор `foreach` можно использовать для итерации всех элементов массива, класса коллекции .NET Framework либо любого класса или структуры, реализующих интерфейс <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="af6f8-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af6f8-105">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="af6f8-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af6f8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="af6f8-106">Example</span></span>  
 <span data-ttu-id="af6f8-107">В этом примере показано, как напечатать аргументы командной строки с помощью оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="af6f8-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="af6f8-108">См. также</span><span class="sxs-lookup"><span data-stu-id="af6f8-108">See Also</span></span>  
 <xref:System.Array>  
 <xref:System.Collections>  
 [<span data-ttu-id="af6f8-109">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="af6f8-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [<span data-ttu-id="af6f8-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="af6f8-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="af6f8-111">foreach, in</span><span class="sxs-lookup"><span data-stu-id="af6f8-111">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="af6f8-112">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="af6f8-112">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="af6f8-113">Практическое руководство. Отображение аргументов командной строки</span><span class="sxs-lookup"><span data-stu-id="af6f8-113">How to: Display Command Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [<span data-ttu-id="af6f8-114">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="af6f8-114">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
