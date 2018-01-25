---
title: "-out (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8ca85293086f8747cc4aaff02e7d9b5628b1e88a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-out-c-compiler-options"></a><span data-ttu-id="ce744-102">-out (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="ce744-102">-out (C# Compiler Options)</span></span>
<span data-ttu-id="ce744-103">Параметр **-out** задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="ce744-103">The **-out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce744-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce744-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce744-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ce744-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="ce744-106">Имя выходного файла, создаваемого компилятором.</span><span class="sxs-lookup"><span data-stu-id="ce744-106">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce744-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce744-107">Remarks</span></span>  
 <span data-ttu-id="ce744-108">В командной строке можно указать несколько выходных файлов для компиляции.</span><span class="sxs-lookup"><span data-stu-id="ce744-108">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="ce744-109">После параметра компилятора **-out** нужно указать один или несколько файлов исходного кода.</span><span class="sxs-lookup"><span data-stu-id="ce744-109">The compiler expects to find one or more source code files following the **-out** option.</span></span> <span data-ttu-id="ce744-110">Все указанные файлы исходного кода будут скомпилированы в выходной файл, заданный параметром **-out**.</span><span class="sxs-lookup"><span data-stu-id="ce744-110">Then, all source code files will be compiled into the output file specified by that **-out** option.</span></span>  
  
 <span data-ttu-id="ce744-111">Укажите полное имя и расширение файла, который требуется создать.</span><span class="sxs-lookup"><span data-stu-id="ce744-111">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="ce744-112">Если имя выходного файла не указано:</span><span class="sxs-lookup"><span data-stu-id="ce744-112">If you do not specify the name of the output file:</span></span>  
  
-   <span data-ttu-id="ce744-113">EXE-файлу будет присвоено имя файла исходного кода, который содержит метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="ce744-113">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
-   <span data-ttu-id="ce744-114">DLL-файлы и NETMODULE-файлы берут имя из первого файла исходного кода.</span><span class="sxs-lookup"><span data-stu-id="ce744-114">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="ce744-115">Файл исходного кода, используемый для компиляции одного выходного файла, не может использоваться в рамках той же компиляции для создания другого выходного файла.</span><span class="sxs-lookup"><span data-stu-id="ce744-115">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="ce744-116">При создании нескольких выходных файлов путем компиляции из командной строки имейте в виду, что из выходных файлов сборкой может быть только один, а именно первый выходной файл, явно или неявно заданный с помощью параметра **-out**.</span><span class="sxs-lookup"><span data-stu-id="ce744-116">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **-out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="ce744-117">Все модули, созданные в процессе компиляции, будут связаны со сборкой, полученной в результате этого процесса.</span><span class="sxs-lookup"><span data-stu-id="ce744-117">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="ce744-118">С помощью [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) можно просмотреть связанные файлы в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="ce744-118">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="ce744-119">Параметр компилятора -out обязателен, если требуется установить EXE-файл в качестве целевого для дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="ce744-119">The -out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="ce744-120">Дополнительные сведения см. в разделе [Дружественные сборки](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ce744-120">For more information see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ce744-121">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce744-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ce744-122">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="ce744-122">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="ce744-123">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="ce744-123">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="ce744-124">Измените свойство **Имя сборки**.</span><span class="sxs-lookup"><span data-stu-id="ce744-124">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="ce744-125">Установка этого параметра компилятора программным способом: свойство <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> доступно только для чтения и определяется сочетанием типа проекта (исполняемый файл, библиотека и т. д.) и именем сборки.</span><span class="sxs-lookup"><span data-stu-id="ce744-125">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="ce744-126">Чтобы задать имя выходного файла, необходимо изменить одно из этих свойств или одновременно оба свойства.</span><span class="sxs-lookup"><span data-stu-id="ce744-126">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce744-127">Пример</span><span class="sxs-lookup"><span data-stu-id="ce744-127">Example</span></span>  
 <span data-ttu-id="ce744-128">Компиляция `t.cs` и создание выходного файла `t.exe`, а также построение `t2.cs` и создание выходного файла модуля `mymodule.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="ce744-128">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce744-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ce744-129">See Also</span></span>  
 [<span data-ttu-id="ce744-130">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="ce744-130">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="ce744-131">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="ce744-131">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="ce744-132">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="ce744-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
