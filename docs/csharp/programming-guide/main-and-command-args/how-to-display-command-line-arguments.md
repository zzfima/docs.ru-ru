---
title: "Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
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
ms.openlocfilehash: cf8a57cce252b3596f0a19c9df643427615467c6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="07a09-102">Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="07a09-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="07a09-103">Аргументы, предоставляемые исполняемому файлу в командной строке, доступны через необязательный параметр для `Main`.</span><span class="sxs-lookup"><span data-stu-id="07a09-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="07a09-104">Аргументы предоставляются в форме массива строк.</span><span class="sxs-lookup"><span data-stu-id="07a09-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="07a09-105">Каждый элемент массива содержит один аргумент.</span><span class="sxs-lookup"><span data-stu-id="07a09-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="07a09-106">Пробелы между аргументами удаляются.</span><span class="sxs-lookup"><span data-stu-id="07a09-106">White-space between arguments is removed.</span></span> <span data-ttu-id="07a09-107">Например, рассмотрим следующие вызовы из командной строки вымышленного исполняемого файла:</span><span class="sxs-lookup"><span data-stu-id="07a09-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="07a09-108">Ввод в командной строке</span><span class="sxs-lookup"><span data-stu-id="07a09-108">Input on Command-line</span></span>|<span data-ttu-id="07a09-109">Массив строк, передаваемых в метод Main</span><span class="sxs-lookup"><span data-stu-id="07a09-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="07a09-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="07a09-110">**executable.exe a b c**</span></span>|<span data-ttu-id="07a09-111">"a"</span><span class="sxs-lookup"><span data-stu-id="07a09-111">"a"</span></span><br /><br /> <span data-ttu-id="07a09-112">"b"</span><span class="sxs-lookup"><span data-stu-id="07a09-112">"b"</span></span><br /><br /> <span data-ttu-id="07a09-113">"c"</span><span class="sxs-lookup"><span data-stu-id="07a09-113">"c"</span></span>|  
|<span data-ttu-id="07a09-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="07a09-114">**executable.exe one two**</span></span>|<span data-ttu-id="07a09-115">"one"</span><span class="sxs-lookup"><span data-stu-id="07a09-115">"one"</span></span><br /><br /> <span data-ttu-id="07a09-116">"two"</span><span class="sxs-lookup"><span data-stu-id="07a09-116">"two"</span></span>|  
|<span data-ttu-id="07a09-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="07a09-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="07a09-118">"один два"</span><span class="sxs-lookup"><span data-stu-id="07a09-118">"one two"</span></span><br /><br /> <span data-ttu-id="07a09-119">"три"</span><span class="sxs-lookup"><span data-stu-id="07a09-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="07a09-120">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="07a09-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07a09-121">Пример</span><span class="sxs-lookup"><span data-stu-id="07a09-121">Example</span></span>  
 <span data-ttu-id="07a09-122">Этот пример отображает аргументы командной строки, передаваемые в приложение командной строки.</span><span class="sxs-lookup"><span data-stu-id="07a09-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="07a09-123">Показанные выходные данные — первая запись в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="07a09-123">The output shown is for the first entry in the table above.</span></span>  
  
 <span data-ttu-id="07a09-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="07a09-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a09-125">См. также</span><span class="sxs-lookup"><span data-stu-id="07a09-125">See Also</span></span>  
 <span data-ttu-id="07a09-126">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="07a09-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="07a09-127">[Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="07a09-127">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="07a09-128">[Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="07a09-128">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="07a09-129">[Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span><span class="sxs-lookup"><span data-stu-id="07a09-129">[How to: Access Command-Line Arguments Using foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span></span>  
 [<span data-ttu-id="07a09-130">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="07a09-130">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

