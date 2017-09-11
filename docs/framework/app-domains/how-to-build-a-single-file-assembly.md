---
title: "Практическое руководство. Построение однофайловой сборки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a584e6ded79489e5e33b07d02dde618541c6cc8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="8b714-102">Практическое руководство. Построение однофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="8b714-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="8b714-103">Однофайловая сборка, являясь простейшим типом сборки, содержит данные о типе и реализации, а также [манифест сборки](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="8b714-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="8b714-104">Для создания однофайловой сборки можно использовать компиляторы командной строки или [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b714-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="8b714-105">По умолчанию компилятор создает файл сборки с расширением .exe.</span><span class="sxs-lookup"><span data-stu-id="8b714-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]<span data-ttu-id="8b714-106"> для C# и Visual Basic можно использовать только для создания однофайловых сборок.</span><span class="sxs-lookup"><span data-stu-id="8b714-106"> for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="8b714-107">Чтобы создать многофайловую сборку, необходимо использовать компиляторы командной строки или [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] для Visual C++.</span><span class="sxs-lookup"><span data-stu-id="8b714-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="8b714-108">В следующих процедурах показано создани6 однофайловых сборок с помощью компиляторов, работающих в режиме командной строки.</span><span class="sxs-lookup"><span data-stu-id="8b714-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="8b714-109">Создание сборки с расширением .exe</span><span class="sxs-lookup"><span data-stu-id="8b714-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="8b714-110">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b714-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="8b714-111">\<*команда компилятора*> \<*имя модуля*></span><span class="sxs-lookup"><span data-stu-id="8b714-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="8b714-112">В этой команде *команда компилятора* — команда компилятора для языка, используемого в модуле кода, а *имя модуля* — имя компилируемого в сборку модуля кода.</span><span class="sxs-lookup"><span data-stu-id="8b714-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="8b714-113">В следующем примере создается сборка с именем `myCode.exe` из модуля кода с именем `myCode`.</span><span class="sxs-lookup"><span data-stu-id="8b714-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="8b714-114">Создание сборки с расширением .exe и указание имени выходного файла</span><span class="sxs-lookup"><span data-stu-id="8b714-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="8b714-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b714-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="8b714-116">\<*команда компилятора*> **/out:**\<*имя файла*> \<*имя модуля*></span><span class="sxs-lookup"><span data-stu-id="8b714-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="8b714-117">В этой команде *команда компилятора* — команда компилятора для языка, используемого в модуле кода, *имя файла* — имя выходного файла, а *имя модуля* — имя компилируемого в сборку модуля кода.</span><span class="sxs-lookup"><span data-stu-id="8b714-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="8b714-118">В следующем примере создается сборка с именем `myAssembly.exe` из модуля кода с именем `myCode`.</span><span class="sxs-lookup"><span data-stu-id="8b714-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="8b714-119">Создание библиотечных сборок</span><span class="sxs-lookup"><span data-stu-id="8b714-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="8b714-120">Библиотечная сборка аналогична библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="8b714-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="8b714-121">Библиотечная сборка аналогична библиотеке классов. Она содержит типы, на которые имеются ссылки в других сборках, но не имеет точки входа, с которой начинается выполнение.</span><span class="sxs-lookup"><span data-stu-id="8b714-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="8b714-122">Создание библиотечной сборки</span><span class="sxs-lookup"><span data-stu-id="8b714-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="8b714-123">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b714-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="8b714-124">\<*команда компилятора*> **/t:library** \<*имя модуля*></span><span class="sxs-lookup"><span data-stu-id="8b714-124">\<*compiler command*> **/t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="8b714-125">В этой команде *команда компилятора* — команда компилятора для языка, используемого в модуле кода, а *имя модуля* — имя компилируемого в сборку модуля кода.</span><span class="sxs-lookup"><span data-stu-id="8b714-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="8b714-126">Можно также использовать другие параметры компилятора, такие как **/out:**.</span><span class="sxs-lookup"><span data-stu-id="8b714-126">You can also use other compiler options, such as the **/out:** option.</span></span>  
  
 <span data-ttu-id="8b714-127">В следующем примере создается библиотечная сборка с именем `myCodeAssembly.dll` из модуля кода с именем `myCode`.</span><span class="sxs-lookup"><span data-stu-id="8b714-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b714-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8b714-128">See Also</span></span>  
 <span data-ttu-id="8b714-129">[Создание сборок](../../../docs/framework/app-domains/create-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="8b714-129">[Creating Assemblies](../../../docs/framework/app-domains/create-assemblies.md) </span></span>  
 <span data-ttu-id="8b714-130">[Многофайловые сборки](../../../docs/framework/app-domains/multifile-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="8b714-130">[Multifile Assemblies](../../../docs/framework/app-domains/multifile-assemblies.md) </span></span>  
 <span data-ttu-id="8b714-131">[Практическое руководство. Создание многофайловой сборки](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="8b714-131">[How to: Build a Multifile Assembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span></span>  
 [<span data-ttu-id="8b714-132">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="8b714-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

