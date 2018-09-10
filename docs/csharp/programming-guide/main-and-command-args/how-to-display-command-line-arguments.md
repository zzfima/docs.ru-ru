---
title: Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: a6067482b4a225abc31592affb2cfab38847cd53
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502676"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="24a93-102">Практическое руководство. Отображение аргументов командной строки (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="24a93-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="24a93-103">Аргументы, предоставляемые исполняемому файлу в командной строке, доступны через необязательный параметр для `Main`.</span><span class="sxs-lookup"><span data-stu-id="24a93-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="24a93-104">Аргументы предоставляются в форме массива строк.</span><span class="sxs-lookup"><span data-stu-id="24a93-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="24a93-105">Каждый элемент массива содержит один аргумент.</span><span class="sxs-lookup"><span data-stu-id="24a93-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="24a93-106">Пробелы между аргументами удаляются.</span><span class="sxs-lookup"><span data-stu-id="24a93-106">White-space between arguments is removed.</span></span> <span data-ttu-id="24a93-107">Например, рассмотрим следующие вызовы из командной строки вымышленного исполняемого файла:</span><span class="sxs-lookup"><span data-stu-id="24a93-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="24a93-108">Ввод в командной строке</span><span class="sxs-lookup"><span data-stu-id="24a93-108">Input on Command-line</span></span>|<span data-ttu-id="24a93-109">Массив строк, передаваемых в метод Main</span><span class="sxs-lookup"><span data-stu-id="24a93-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="24a93-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="24a93-110">**executable.exe a b c**</span></span>|<span data-ttu-id="24a93-111">"a"</span><span class="sxs-lookup"><span data-stu-id="24a93-111">"a"</span></span><br /><br /> <span data-ttu-id="24a93-112">"b"</span><span class="sxs-lookup"><span data-stu-id="24a93-112">"b"</span></span><br /><br /> <span data-ttu-id="24a93-113">"c"</span><span class="sxs-lookup"><span data-stu-id="24a93-113">"c"</span></span>|  
|<span data-ttu-id="24a93-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="24a93-114">**executable.exe one two**</span></span>|<span data-ttu-id="24a93-115">"one"</span><span class="sxs-lookup"><span data-stu-id="24a93-115">"one"</span></span><br /><br /> <span data-ttu-id="24a93-116">"two"</span><span class="sxs-lookup"><span data-stu-id="24a93-116">"two"</span></span>|  
|<span data-ttu-id="24a93-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="24a93-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="24a93-118">"один два"</span><span class="sxs-lookup"><span data-stu-id="24a93-118">"one two"</span></span><br /><br /> <span data-ttu-id="24a93-119">"три"</span><span class="sxs-lookup"><span data-stu-id="24a93-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="24a93-120">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="24a93-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="24a93-121">Пример</span><span class="sxs-lookup"><span data-stu-id="24a93-121">Example</span></span>  
 <span data-ttu-id="24a93-122">Этот пример отображает аргументы командной строки, передаваемые в приложение командной строки.</span><span class="sxs-lookup"><span data-stu-id="24a93-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="24a93-123">Показанные выходные данные — первая запись в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="24a93-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="24a93-124">См. также</span><span class="sxs-lookup"><span data-stu-id="24a93-124">See Also</span></span>

- [<span data-ttu-id="24a93-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="24a93-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="24a93-126">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="24a93-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [<span data-ttu-id="24a93-127">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="24a93-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [<span data-ttu-id="24a93-128">Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach</span><span class="sxs-lookup"><span data-stu-id="24a93-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
- [<span data-ttu-id="24a93-129">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="24a93-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
