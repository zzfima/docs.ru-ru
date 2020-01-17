---
title: Руководство по программированию на C#. Отображение аргументов командной строки
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 210dad71220572535a0325fac925b0453b0d4e03
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712030"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="d9bff-102">Руководство по программированию на C#. Отображение аргументов командной строки</span><span class="sxs-lookup"><span data-stu-id="d9bff-102">How to display command line arguments (C# Programming Guide)</span></span>
<span data-ttu-id="d9bff-103">Аргументы, предоставляемые исполняемому файлу в командной строке, доступны через необязательный параметр для `Main`.</span><span class="sxs-lookup"><span data-stu-id="d9bff-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="d9bff-104">Аргументы предоставляются в форме массива строк.</span><span class="sxs-lookup"><span data-stu-id="d9bff-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="d9bff-105">Каждый элемент массива содержит один аргумент.</span><span class="sxs-lookup"><span data-stu-id="d9bff-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="d9bff-106">Пробелы между аргументами удаляются.</span><span class="sxs-lookup"><span data-stu-id="d9bff-106">White-space between arguments is removed.</span></span> <span data-ttu-id="d9bff-107">Например, рассмотрим следующие вызовы из командной строки вымышленного исполняемого файла:</span><span class="sxs-lookup"><span data-stu-id="d9bff-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="d9bff-108">Ввод в командной строке</span><span class="sxs-lookup"><span data-stu-id="d9bff-108">Input on Command-line</span></span>|<span data-ttu-id="d9bff-109">Массив строк, передаваемых в метод Main</span><span class="sxs-lookup"><span data-stu-id="d9bff-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="d9bff-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="d9bff-110">**executable.exe a b c**</span></span>|<span data-ttu-id="d9bff-111">"a"</span><span class="sxs-lookup"><span data-stu-id="d9bff-111">"a"</span></span><br /><br /> <span data-ttu-id="d9bff-112">"b"</span><span class="sxs-lookup"><span data-stu-id="d9bff-112">"b"</span></span><br /><br /> <span data-ttu-id="d9bff-113">"c"</span><span class="sxs-lookup"><span data-stu-id="d9bff-113">"c"</span></span>|  
|<span data-ttu-id="d9bff-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="d9bff-114">**executable.exe one two**</span></span>|<span data-ttu-id="d9bff-115">"one"</span><span class="sxs-lookup"><span data-stu-id="d9bff-115">"one"</span></span><br /><br /> <span data-ttu-id="d9bff-116">"two"</span><span class="sxs-lookup"><span data-stu-id="d9bff-116">"two"</span></span>|  
|<span data-ttu-id="d9bff-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="d9bff-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="d9bff-118">"один два"</span><span class="sxs-lookup"><span data-stu-id="d9bff-118">"one two"</span></span><br /><br /> <span data-ttu-id="d9bff-119">"три"</span><span class="sxs-lookup"><span data-stu-id="d9bff-119">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d9bff-120">При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="d9bff-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9bff-121">Пример</span><span class="sxs-lookup"><span data-stu-id="d9bff-121">Example</span></span>  
 <span data-ttu-id="d9bff-122">Этот пример отображает аргументы командной строки, передаваемые в приложение командной строки.</span><span class="sxs-lookup"><span data-stu-id="d9bff-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="d9bff-123">Показанные выходные данные — первая запись в таблице выше.</span><span class="sxs-lookup"><span data-stu-id="d9bff-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="d9bff-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d9bff-124">See also</span></span>

- [<span data-ttu-id="d9bff-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d9bff-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d9bff-126">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="d9bff-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="d9bff-127">Main() и аргументы командной строки</span><span class="sxs-lookup"><span data-stu-id="d9bff-127">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="d9bff-128">Значения, возвращаемые методом main()</span><span class="sxs-lookup"><span data-stu-id="d9bff-128">Main() Return Values</span></span>](./main-return-values.md)
