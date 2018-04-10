---
title: '#line (справочник по C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d2f42915d214349eebff40949482d7f603c0c2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="line-c-reference"></a><span data-ttu-id="813f6-102">#line (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="813f6-102">#line (C# Reference)</span></span>
<span data-ttu-id="813f6-103">Директива `#line` позволяет изменять номер строки компилятора и при необходимости имя файла, в который будут выводиться ошибки и предупреждения.</span><span class="sxs-lookup"><span data-stu-id="813f6-103">`#line` lets you modify the compiler's line number and (optionally) the file name output for errors and warnings.</span></span> <span data-ttu-id="813f6-104">В этом примере показано, как включить в отчет два предупреждения, связанные с номерами строк.</span><span class="sxs-lookup"><span data-stu-id="813f6-104">This example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="813f6-105">Директива `#line 200` принудительно устанавливает номер строки 200 (по умолчанию используется номер 7). До выполнения следующей директивы #line в отчете будет указываться имя файла "Special".</span><span class="sxs-lookup"><span data-stu-id="813f6-105">The `#line 200` directive forces the line number to be 200 (although the default is #7) and until the next #line directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="813f6-106">Директива #line по умолчанию восстанавливает нумерацию строк в исходное состояние с учетом строк, номера которых были изменены с помощью предшествующей директивы.</span><span class="sxs-lookup"><span data-stu-id="813f6-106">The #line default directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>  
  
```csharp
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="813f6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="813f6-107">Remarks</span></span>  
 <span data-ttu-id="813f6-108">Директива `#line` может использоваться на автоматизированном промежуточном этапе процесса построения.</span><span class="sxs-lookup"><span data-stu-id="813f6-108">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="813f6-109">Например, если строки были удалены из первоначального файла с исходным кодом, но вам по-прежнему требуется создавать выходные файлы компилятора на основе изначальной нумерации строк в файле, можно удалить строки и затем смоделировать их первичную нумерацию с помощью директивы `#line`.</span><span class="sxs-lookup"><span data-stu-id="813f6-109">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>  
  
 <span data-ttu-id="813f6-110">Директива `#line hidden` скрывает последующие строки для отладчика. В этом случае при пошаговой проверке кода разработчиком все строки между `#line hidden` и следующей директивой `#line` (кроме случаев, когда это также директива `#line hidden`) будут пропущены.</span><span class="sxs-lookup"><span data-stu-id="813f6-110">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="813f6-111">Этот параметр также можно использовать для того, чтобы дать ASP.NET возможность различать определяемый пользователем и создаваемый компьютером код.</span><span class="sxs-lookup"><span data-stu-id="813f6-111">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="813f6-112">В основном эта функция используется в ASP.NET, но также может быть полезна и в других генераторах исходного кода.</span><span class="sxs-lookup"><span data-stu-id="813f6-112">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>  
  
 <span data-ttu-id="813f6-113">Директива `#line hidden` не влияет на имена файлов и номера строк в отчетах об ошибках.</span><span class="sxs-lookup"><span data-stu-id="813f6-113">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="813f6-114">Это значит, что при обнаружении ошибки в скрытом блоке компилятор укажет в отчете текущие имя файла и номер строки, где найдена ошибка.</span><span class="sxs-lookup"><span data-stu-id="813f6-114">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>  
  
 <span data-ttu-id="813f6-115">Директива `#line filename` задает имя файла, которое будет отображаться в выходных данных компилятора.</span><span class="sxs-lookup"><span data-stu-id="813f6-115">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="813f6-116">По умолчанию используется фактическое имя файла с исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="813f6-116">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="813f6-117">Имя файла должно заключаться в двойные кавычки (" "). Перед ним должен указываться номер строки.</span><span class="sxs-lookup"><span data-stu-id="813f6-117">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>  
  
 <span data-ttu-id="813f6-118">Файл с исходным кодом может содержать любое количество директив `#line`.</span><span class="sxs-lookup"><span data-stu-id="813f6-118">A source code file can have any number of `#line` directives.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="813f6-119">Пример 1</span><span class="sxs-lookup"><span data-stu-id="813f6-119">Example 1</span></span>  
 <span data-ttu-id="813f6-120">В следующем примере демонстрируется, как отладчик игнорирует скрытые строки кода.</span><span class="sxs-lookup"><span data-stu-id="813f6-120">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="813f6-121">При выполнении этого примера будут показаны три строки текста.</span><span class="sxs-lookup"><span data-stu-id="813f6-121">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="813f6-122">Тем не менее, если задать точку останова, как показано в этом примере, и нажать клавишу F10 для пошаговой отладки кода, вы увидите, что отладчик игнорирует скрытую строку.</span><span class="sxs-lookup"><span data-stu-id="813f6-122">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="813f6-123">Обратите внимание, что даже если точка останова установлена на скрытой строке, отладчик по-прежнему будет игнорировать ее.</span><span class="sxs-lookup"><span data-stu-id="813f6-123">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>  
  
```csharp
// preprocessor_linehidden.cs  
using System;  
class MainClass   
{  
    static void Main()   
    {  
        Console.WriteLine("Normal line #1."); // Set break point here.  
#line hidden  
        Console.WriteLine("Hidden line.");  
#line default  
        Console.WriteLine("Normal line #2.");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="813f6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="813f6-124">See Also</span></span>  
 [<span data-ttu-id="813f6-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="813f6-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="813f6-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="813f6-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="813f6-127">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="813f6-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
