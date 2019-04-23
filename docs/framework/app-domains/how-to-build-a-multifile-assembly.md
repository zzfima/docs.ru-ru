---
title: Как выполнить Создание многофайловой сборки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcc451903f7fbf7f82e2ed64834d26e605a0c069
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187802"
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="825a9-102">Как выполнить Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="825a9-102">How to: Build a Multifile Assembly</span></span>
<span data-ttu-id="825a9-103">В этой статье рассматривается порядок создания многофайловой сборки и приводится код, иллюстрирующий каждый шаг процедуры.</span><span class="sxs-lookup"><span data-stu-id="825a9-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="825a9-104">Интегрированную среду разработки в Visual Studio для C# и Visual Basic можно использовать только для создания однофайловых сборок.</span><span class="sxs-lookup"><span data-stu-id="825a9-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="825a9-105">Если требуется создать многофайловую сборку, необходимо использовать компиляторы командной строки или Visual Studio с Visual C++.</span><span class="sxs-lookup"><span data-stu-id="825a9-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span>

### <a name="to-create-a-multifile-assembly"></a><span data-ttu-id="825a9-106">Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="825a9-106">To create a multifile assembly</span></span>

01. <span data-ttu-id="825a9-107">Скомпилируйте в модули кода все файлы, содержащие пространства имен, на которые имеются ссылки в других модулях сборки.</span><span class="sxs-lookup"><span data-stu-id="825a9-107">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="825a9-108">По умолчанию для модулей кода используется расширение .netmodule.</span><span class="sxs-lookup"><span data-stu-id="825a9-108">The default extension for code modules is .netmodule.</span></span>

    <span data-ttu-id="825a9-109">Предположим, например, что файл `Stringer` имеет пространство имен `myStringer`, которое содержит класс с именем `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="825a9-109">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="825a9-110">Класс `Stringer` содержит метод с именем `StringerMethod`, который выводит отдельную строку на консоль.</span><span class="sxs-lookup"><span data-stu-id="825a9-110">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
    [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
    [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]

    <span data-ttu-id="825a9-111">Для компиляции этого кода используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="825a9-111">Use the following command to compile this code:</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
    [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
    [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]

    <span data-ttu-id="825a9-112">Задание параметра *module* вместе с параметром компилятора **/t:** указывает на то, что результатом компиляции является модуль, а не сборка.</span><span class="sxs-lookup"><span data-stu-id="825a9-112">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="825a9-113">Компилятор создает модуль с именем `Stringer.netmodule`, который можно добавить в сборку.</span><span class="sxs-lookup"><span data-stu-id="825a9-113">The compiler produces a module called `Stringer.netmodule`, which can be added to an assembly.</span></span>

02. <span data-ttu-id="825a9-114">Скомпилируйте все другие модули, используя соответствующие параметры компилятора для указания других модулей, на которые имеются ссылки в коде.</span><span class="sxs-lookup"><span data-stu-id="825a9-114">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="825a9-115">На этом этапе используется параметр компилятора **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="825a9-115">This step uses the **/addmodule** compiler option.</span></span>

    <span data-ttu-id="825a9-116">В следующем примере модуль кода с именем `Client` имеет метод точки входа `Main`, который ссылается на метод в модуле `Stringer.dll`, созданном на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="825a9-116">In the following example, a code module called `Client` has an entry point `Main` method that references a method in the `Stringer.dll` module created in step 1.</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
    [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
    [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]

    <span data-ttu-id="825a9-117">Для компиляции этого кода используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="825a9-117">Use the following command to compile this code:</span></span>

    [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
    [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
    [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]

    <span data-ttu-id="825a9-118">Укажите параметр **/t:module**, поскольку этот модуль будет добавлен в сборку на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="825a9-118">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="825a9-119">Также укажите параметр **/addmodule**, поскольку код в `Client` ссылается на пространство имен, созданное кодом в `Stringer.netmodule`.</span><span class="sxs-lookup"><span data-stu-id="825a9-119">Specify the **/addmodule** option because the code in `Client` references a namespace created by the code in `Stringer.netmodule`.</span></span> <span data-ttu-id="825a9-120">Компилятор создает модуль с именем `Client.netmodule`, который содержит ссылку на модуль `Stringer.netmodule`.</span><span class="sxs-lookup"><span data-stu-id="825a9-120">The compiler produces a module called `Client.netmodule` that contains a reference to another module, `Stringer.netmodule`.</span></span>

    >[!NOTE]
    ><span data-ttu-id="825a9-121">Компиляторы C# и Visual Basic поддерживают непосредственное создание многофайловых сборок с помощью следующих двух синтаксических структур.</span><span class="sxs-lookup"><span data-stu-id="825a9-121">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>
    >
    >- <span data-ttu-id="825a9-122">Для создания сборки из двух файлов используются две компиляции:</span><span class="sxs-lookup"><span data-stu-id="825a9-122">Two compilations create a two-file assembly:</span></span>
    >
    >    [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
    >    [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
    >    [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]
    >
    >- <span data-ttu-id="825a9-123">При создании сборки из двух файлов используется одна компиляция:</span><span class="sxs-lookup"><span data-stu-id="825a9-123">One compilation creates a two-file assembly:</span></span>
    >
    >    [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
    >    [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
    >    [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]

03. <span data-ttu-id="825a9-124">Используйте [компоновщик сборок (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) для создания выходного файла, содержащего манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="825a9-124">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="825a9-125">Выходной файл содержит справочную информацию для всех модулей или ресурсов, входящих в сборку.</span><span class="sxs-lookup"><span data-stu-id="825a9-125">This file contains reference information for all modules or resources that are part of the assembly.</span></span>

    <span data-ttu-id="825a9-126">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="825a9-126">At the command prompt, type the following command:</span></span>

    <span data-ttu-id="825a9-127">**al** \<*имя модуля*> \<*имя модуля*> …</span><span class="sxs-lookup"><span data-stu-id="825a9-127">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="825a9-128">**/main:**\<*имя метода*> **/out:**\<*имя файла*> **/target:**\<*тип файла сборки*></span><span class="sxs-lookup"><span data-stu-id="825a9-128">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>

    <span data-ttu-id="825a9-129">В этой команде в аргументах *имя модуля* задаются имена всех модулей, которые будут включены в сборку.</span><span class="sxs-lookup"><span data-stu-id="825a9-129">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="825a9-130">В параметре **/main:** указывается имя метода, являющегося точкой входа сборки.</span><span class="sxs-lookup"><span data-stu-id="825a9-130">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="825a9-131">В параметре **/out:** задается имя выходного файла, содержащего метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="825a9-131">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="825a9-132">В параметре **/target:** указывается, что сборка является исполняемым файлом консольного приложения (EXE), исполняемым файлом Windows (WIN) или же файлом библиотеки (LIB).</span><span class="sxs-lookup"><span data-stu-id="825a9-132">The **/target:** option specifies that the assembly is a console application executable (.exe) file, a Windows executable (.win) file, or a library (.lib) file.</span></span>

    <span data-ttu-id="825a9-133">В следующем примере средство Al.exe создает сборку, являющуюся консольным приложением с именем `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="825a9-133">In the following example, Al.exe creates an assembly that is a console application executable called `myAssembly.exe`.</span></span> <span data-ttu-id="825a9-134">Приложение состоит из двух модулей с именами `Client.netmodule` и `Stringer.netmodule`, а также исполняемого файла с именем `myAssembly.exe,`, который содержит только метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="825a9-134">The application consists of two modules called `Client.netmodule` and `Stringer.netmodule`, and the executable file called `myAssembly.exe,` which contains only assembly metadata.</span></span> <span data-ttu-id="825a9-135">Точкой входа сборки является метод `Main` класса `MainClientApp`, который находится в библиотеке`Client.dll`.</span><span class="sxs-lookup"><span data-stu-id="825a9-135">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in `Client.dll`.</span></span>

    ```
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    <span data-ttu-id="825a9-136">Для проверки содержимого сборки или определения, является ли файл сборкой или модулем, можно использовать средство [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="825a9-136">You can use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>

## <a name="see-also"></a><span data-ttu-id="825a9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="825a9-137">See also</span></span>

- [<span data-ttu-id="825a9-138">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="825a9-138">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="825a9-139">Практическое руководство. Просмотр содержимого сборки</span><span class="sxs-lookup"><span data-stu-id="825a9-139">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)
- [<span data-ttu-id="825a9-140">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="825a9-140">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="825a9-141">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="825a9-141">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
