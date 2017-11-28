---
title: "Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6ae495eef227c6e4d9fb9ca0d4d0c031163fd52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="445e6-102">Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="445e6-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="445e6-103">Аргументы, предоставляемые исполняемому файлу в командной строке, доступны через необязательный параметр для `Main`.</span><span class="sxs-lookup"><span data-stu-id="445e6-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="445e6-104">Аргументы предоставляются в форме массива строк.</span><span class="sxs-lookup"><span data-stu-id="445e6-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="445e6-105">Каждый элемент массива содержит один аргумент.</span><span class="sxs-lookup"><span data-stu-id="445e6-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="445e6-106">Пробелы между аргументами удаляются.</span><span class="sxs-lookup"><span data-stu-id="445e6-106">White-space between arguments is removed.</span></span> <span data-ttu-id="445e6-107">Например, рассмотрим следующие вызовы из командной строки вымышленного исполняемого файла:</span><span class="sxs-lookup"><span data-stu-id="445e6-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="445e6-108">Ввод в командной строке</span><span class="sxs-lookup"><span data-stu-id="445e6-108">Input on Command-line</span></span>|<span data-ttu-id="445e6-109">Массив строк, передаваемых в метод Main</span><span class="sxs-lookup"><span data-stu-id="445e6-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="445e6-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="445e6-110">**executable.exe a b c**</span></span>|<span data-ttu-id="445e6-111">"a"</span><span class="sxs-lookup"><span data-stu-id="445e6-111">"a"</span></span><br /><br /> <span data-ttu-id="445e6-112">"b"</span><span class="sxs-lookup"><span data-stu-id="445e6-112">"b"</span></span><br /><br /> <span data-ttu-id="445e6-113">"c"</span><span class="sxs-lookup"><span data-stu-id="445e6-113">"c"</span></span>|  
|<span data-ttu-id="445e6-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="445e6-114">**executable.exe one two**</span></span>|<span data-ttu-id="445e6-115">"one"</span><span class="sxs-lookup"><span data-stu-id="445e6-115">"one"</span></span><br /><br /> <span data-ttu-id="445e6-116">"two"</span><span class="sxs-lookup"><span data-stu-id="445e6-116">"two"</span></span>|  
|<span data-ttu-id="445e6-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="445e6-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="445e6-118">"один два"</span><span class="sxs-lookup"><span data-stu-id="445e6-118">"one two"</span></span><br /><br /> <span data-ttu-id="445e6-119">"три"</span><span class="sxs-lookup"><span data-stu-id="445e6-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="445e6-120">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="445e6-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="445e6-121">Пример</span><span class="sxs-lookup"><span data-stu-id="445e6-121">Example</span></span>  
 <span data-ttu-id="445e6-122">Этот пример отображает аргументы командной строки, передаваемые в приложение командной строки.</span><span class="sxs-lookup"><span data-stu-id="445e6-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="445e6-123">Показанные выходные данные — первая запись в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="445e6-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="445e6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="445e6-124">See Also</span></span>  
 [<span data-ttu-id="445e6-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="445e6-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="445e6-126">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="445e6-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [<span data-ttu-id="445e6-127">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="445e6-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="445e6-128">Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach</span><span class="sxs-lookup"><span data-stu-id="445e6-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [<span data-ttu-id="445e6-129">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="445e6-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
