---
title: 'How to: Build a multifile assembly'
ms.date: 08/20/2019
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
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
ms.openlocfilehash: 0f8c6d57425657e321d80f9edffa20f27bc28770
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429566"
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="673c5-102">How to: Build a multifile assembly</span><span class="sxs-lookup"><span data-stu-id="673c5-102">How to: Build a multifile assembly</span></span>

<span data-ttu-id="673c5-103">В этой статье рассматривается порядок создания многофайловой сборки и приводится код, иллюстрирующий каждый шаг процедуры.</span><span class="sxs-lookup"><span data-stu-id="673c5-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="673c5-104">Интегрированную среду разработки в Visual Studio для C# и Visual Basic можно использовать только для создания однофайловых сборок.</span><span class="sxs-lookup"><span data-stu-id="673c5-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="673c5-105">Если требуется создать многофайловую сборку, необходимо использовать компиляторы командной строки или Visual Studio с Visual C++.</span><span class="sxs-lookup"><span data-stu-id="673c5-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="673c5-106">Многофайловые сборки поддерживаются только .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="673c5-106">Multifile assemblies are supported by .NET Framework only.</span></span>

## <a name="create-a-multifile-assembly"></a><span data-ttu-id="673c5-107">Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="673c5-107">Create a multifile assembly</span></span>

1. <span data-ttu-id="673c5-108">Скомпилируйте в модули кода все файлы, содержащие пространства имен, на которые имеются ссылки в других модулях сборки.</span><span class="sxs-lookup"><span data-stu-id="673c5-108">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="673c5-109">По умолчанию для модулей кода используется расширение *NETMODULE*.</span><span class="sxs-lookup"><span data-stu-id="673c5-109">The default extension for code modules is *.netmodule*.</span></span>

   <span data-ttu-id="673c5-110">Предположим, например, что файл `Stringer` имеет пространство имен `myStringer`, которое содержит класс с именем `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="673c5-110">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="673c5-111">Класс `Stringer` содержит метод с именем `StringerMethod`, который выводит отдельную строку на консоль.</span><span class="sxs-lookup"><span data-stu-id="673c5-111">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>

   ```cpp
   // Assembly building example in the .NET Framework.
   using namespace System;

   namespace myStringer
   {
       public ref class Stringer
       {
       public:
           void StringerMethod()
           {
               System::Console::WriteLine("This is a line from StringerMethod.");
           }
       };
   }
   ```

   ```csharp
   // Assembly building example in the .NET Framework.
   using System;

   namespace myStringer
   {
       public class Stringer
       {
           public void StringerMethod()
           {
               System.Console.WriteLine("This is a line from StringerMethod.");
           }
       }
   }
   ```

   ```vb
   ' Assembly building example in the .NET Framework.
   Namespace myStringer
       Public Class Stringer
           Public Sub StringerMethod()
               System.Console.WriteLine("This is a line from StringerMethod.")
           End Sub
       End Class
   End Namespace
   ```

2. <span data-ttu-id="673c5-112">Для компиляции этого кода используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="673c5-112">Use the following command to compile this code:</span></span>

   ```cpp
   cl /clr:pure /LN Stringer.cpp
   ```

   ```csharp
   csc /t:module Stringer.cs
   ```

   ```vb
   vbc /t:module Stringer.vb
   ```

   <span data-ttu-id="673c5-113">Задание параметра *module* вместе с параметром компилятора **/t:** указывает на то, что результатом компиляции является модуль, а не сборка.</span><span class="sxs-lookup"><span data-stu-id="673c5-113">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="673c5-114">Компилятор создает модуль с именем *Stringer.netmodule*, который можно добавить в сборку.</span><span class="sxs-lookup"><span data-stu-id="673c5-114">The compiler produces a module called *Stringer.netmodule*, which can be added to an assembly.</span></span>

3. <span data-ttu-id="673c5-115">Скомпилируйте все другие модули, используя соответствующие параметры компилятора для указания других модулей, на которые имеются ссылки в коде.</span><span class="sxs-lookup"><span data-stu-id="673c5-115">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="673c5-116">На этом этапе используется параметр компилятора **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="673c5-116">This step uses the **/addmodule** compiler option.</span></span>

   <span data-ttu-id="673c5-117">В следующем примере модуль кода с именем *Client* имеет метод точки входа `Main`, который ссылается на метод в модуле *Stringer.dll*, созданном на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="673c5-117">In the following example, a code module called *Client* has an entry point `Main` method that references a method in the *Stringer.dll* module created in step 1.</span></span>

   ```cpp
   #using "Stringer.netmodule"

   using namespace System;
   using namespace myStringer; //The namespace created in Stringer.netmodule.

   ref class MainClientApp
   {
       // Static method Main is the entry point method.
   public:
       static void Main()
       {
           Stringer^ myStringInstance = gcnew Stringer();
           Console::WriteLine("Client code executes");
           myStringInstance->StringerMethod();
       }
   };

   int main()
   {
       MainClientApp::Main();
   }
   ```

   ```csharp
   using System;
   using myStringer;

   class MainClientApp
   {
       // Static method Main is the entry point method.
       public static void Main()
       {
           Stringer myStringInstance = new Stringer();
           Console.WriteLine("Client code executes");
           myStringInstance.StringerMethod();
       }
   }
   ```

   ```vb
   Imports myStringer

   Class MainClientApp
       ' Static method Main is the entry point method.
       Public Shared Sub Main()
           Dim myStringInstance As New Stringer()
           Console.WriteLine("Client code executes")
           myStringInstance.StringerMethod()
       End Sub
   End Class
   ```

4. <span data-ttu-id="673c5-118">Для компиляции этого кода используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="673c5-118">Use the following command to compile this code:</span></span>

   ```cpp
   cl /clr:pure /FUStringer.netmodule /LN Client.cpp
   ```

   ```csharp
   csc /addmodule:Stringer.netmodule /t:module Client.cs
   ```

   ```vb
   vbc /addmodule:Stringer.netmodule /t:module Client.vb
   ```

   <span data-ttu-id="673c5-119">Укажите параметр **/t:module**, поскольку этот модуль будет добавлен в сборку на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="673c5-119">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="673c5-120">Также укажите параметр **/addmodule**, так как код в *Client* ссылается на пространство имен, созданное кодом в *Stringer.netmodule*.</span><span class="sxs-lookup"><span data-stu-id="673c5-120">Specify the **/addmodule** option because the code in *Client* references a namespace created by the code in *Stringer.netmodule*.</span></span> <span data-ttu-id="673c5-121">Компилятор создает модуль с именем *Client.netmodule*, который содержит ссылку на другой модуль — *Stringer.netmodule*.</span><span class="sxs-lookup"><span data-stu-id="673c5-121">The compiler produces a module called *Client.netmodule* that contains a reference to another module, *Stringer.netmodule*.</span></span>

   > [!NOTE]
   > <span data-ttu-id="673c5-122">Компиляторы C# и Visual Basic поддерживают непосредственное создание многофайловых сборок с помощью следующих двух синтаксических структур.</span><span class="sxs-lookup"><span data-stu-id="673c5-122">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>
   >
   > <span data-ttu-id="673c5-123">Для создания сборки из двух файлов используются две компиляции:</span><span class="sxs-lookup"><span data-stu-id="673c5-123">Two compilations create a two-file assembly:</span></span>
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /t:module Stringer.cs
   >   csc Client.cs /addmodule:Stringer.netmodule
   >   ```
   >
   >   ```vb
   >   vbc /t:module Stringer.vb
   >   vbc Client.vb /addmodule:Stringer.netmodule
   >   ```
   >
   > <span data-ttu-id="673c5-124">При создании сборки из двух файлов используется одна компиляция:</span><span class="sxs-lookup"><span data-stu-id="673c5-124">One compilation creates a two-file assembly:</span></span>
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /out:Client.exe Client.cs /out:Stringer.netmodule Stringer.cs
   >   ```
   >
   >   ```vb
   >   vbc /out:Client.exe Client.vb /out:Stringer.netmodule Stringer.vb
   >   ```

5. <span data-ttu-id="673c5-125">Используйте [компоновщик сборок (Al.exe)](../tools/al-exe-assembly-linker.md) для создания выходного файла, содержащего манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="673c5-125">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="673c5-126">Выходной файл содержит справочную информацию для всех модулей или ресурсов, входящих в сборку.</span><span class="sxs-lookup"><span data-stu-id="673c5-126">This file contains reference information for all modules or resources that are part of the assembly.</span></span>

    <span data-ttu-id="673c5-127">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="673c5-127">At the command prompt, type the following command:</span></span>

    <span data-ttu-id="673c5-128">**al** \<*имя модуля*> \<*имя модуля*> …</span><span class="sxs-lookup"><span data-stu-id="673c5-128">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="673c5-129">**/main:** \<*имя метода*>  **/out:** \<*имя файла*>  **/target:** \<*тип файла сборки*></span><span class="sxs-lookup"><span data-stu-id="673c5-129">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>

    <span data-ttu-id="673c5-130">В этой команде в аргументах *имя модуля* задаются имена всех модулей, которые будут включены в сборку.</span><span class="sxs-lookup"><span data-stu-id="673c5-130">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="673c5-131">В параметре **/main:** указывается имя метода, являющегося точкой входа сборки.</span><span class="sxs-lookup"><span data-stu-id="673c5-131">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="673c5-132">В параметре **/out:** задается имя выходного файла, содержащего метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="673c5-132">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="673c5-133">В параметре **/target:** указывается, что сборка является исполняемым файлом консольного приложения (*EXE*), исполняемым файлом Windows (*WIN*) или же файлом библиотеки (*LIB*).</span><span class="sxs-lookup"><span data-stu-id="673c5-133">The **/target:** option specifies that the assembly is a console application executable (*.exe*) file, a Windows executable (*.win*) file, or a library (*.lib*) file.</span></span>

    <span data-ttu-id="673c5-134">В следующем примере средство *Al.exe* создает сборку, являющуюся исполняемым файлом консольного приложения с именем *myAssembly.exe*.</span><span class="sxs-lookup"><span data-stu-id="673c5-134">In the following example, *Al.exe* creates an assembly that is a console application executable called *myAssembly.exe*.</span></span> <span data-ttu-id="673c5-135">Приложение состоит из двух модулей с именами *Client.netmodule* и *Stringer.netmodule*, а также исполняемого файла *myAssembly.exe*, который содержит только метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="673c5-135">The application consists of two modules called *Client.netmodule* and *Stringer.netmodule*, and the executable file called *myAssembly.exe*, which contains only assembly metadata.</span></span> <span data-ttu-id="673c5-136">Точкой входа сборки является метод `Main` класса `MainClientApp`, который находится в *Client.dll*.</span><span class="sxs-lookup"><span data-stu-id="673c5-136">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in *Client.dll*.</span></span>

    ```cmd
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    <span data-ttu-id="673c5-137">Для проверки содержимого сборки или определения, является ли файл сборкой или модулем, можно использовать средство [MSIL Disassembler (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="673c5-137">You can use the [MSIL Disassembler (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>

## <a name="see-also"></a><span data-ttu-id="673c5-138">См. также</span><span class="sxs-lookup"><span data-stu-id="673c5-138">See also</span></span>

- [<span data-ttu-id="673c5-139">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="673c5-139">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="673c5-140">How to: View assembly contents</span><span class="sxs-lookup"><span data-stu-id="673c5-140">How to: View assembly contents</span></span>](../../standard/assembly/view-contents.md)
- [<span data-ttu-id="673c5-141">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="673c5-141">How the runtime locates assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="673c5-142">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="673c5-142">Multifile assemblies</span></span>](multifile-assemblies.md)
