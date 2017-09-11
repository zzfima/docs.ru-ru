---
title: "Практическое руководство. Просмотр содержимого сборок"
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
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3583e69e90080eb830bb61a5e0c7b6e944f7d654
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="af979-102">Практическое руководство. Просмотр содержимого сборок</span><span class="sxs-lookup"><span data-stu-id="af979-102">How to: View Assembly Contents</span></span>
<span data-ttu-id="af979-103">Можно использовать [Ildasm.exe (дизассемблер IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) для просмотра сведений промежуточного языка MSIL в файле.</span><span class="sxs-lookup"><span data-stu-id="af979-103">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="af979-104">Если анализируемый файл является сборкой, то эти данные могут включать в себя атрибуты сборки, а также ссылки на другие модули и сборки.</span><span class="sxs-lookup"><span data-stu-id="af979-104">If the file being examined is an assembly, this information can include the assembly's attributes, as well as references to other modules and assemblies.</span></span> <span data-ttu-id="af979-105">Эти данные полезны для определения того, является ли файл сборкой или частью сборки и имеет ли он ссылки на другие модули и сборки.</span><span class="sxs-lookup"><span data-stu-id="af979-105">This information can be helpful in determining whether a file is an assembly or part of an assembly, and whether the file has references to other modules or assemblies.</span></span>  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a><span data-ttu-id="af979-106">Отображение содержимого сборки с помощью Ildasm.exe</span><span class="sxs-lookup"><span data-stu-id="af979-106">To display the contents of an assembly using Ildasm.exe</span></span>  
  
1.  <span data-ttu-id="af979-107">В командной строке введите **ildasm** \<*имя сборки*>.</span><span class="sxs-lookup"><span data-stu-id="af979-107">Type **ildasm** \<*assembly name*> at the command prompt.</span></span> <span data-ttu-id="af979-108">Например, следующая команда дизассемблирует сборку `Hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="af979-108">For example, the following command disassembles the `Hello.exe` assembly.</span></span>  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a><span data-ttu-id="af979-109">Просмотр сведений манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="af979-109">To view assembly manifest information</span></span>  
  
1.  <span data-ttu-id="af979-110">Дважды щелкните значок MANIFEST в окне дизассемблера MSIL.</span><span class="sxs-lookup"><span data-stu-id="af979-110">Double-click the MANIFEST icon in the MSIL Disassembler window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af979-111">Пример</span><span class="sxs-lookup"><span data-stu-id="af979-111">Example</span></span>  
 <span data-ttu-id="af979-112">Следующий пример начинается с простой программы "Hello, World".</span><span class="sxs-lookup"><span data-stu-id="af979-112">The following example starts with a basic "Hello, World" program.</span></span> <span data-ttu-id="af979-113">После компиляции программы используйте программу Ildasm.exe, чтобы декомпилировать сборку Hello.exe и просмотреть манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="af979-113">After compiling the program, use Ildasm.exe to disassemble the Hello.exe assembly and view the assembly manifest.</span></span>  
  
 <span data-ttu-id="af979-114">[!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)] [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)] [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="af979-114">[!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)] [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)] [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]</span></span>  
  
 <span data-ttu-id="af979-115">Выполните команду ildasm.exe над сборкой Hello.exe и дважды щелкните значок MANIFEST в окне IL DASM, чтобы получить следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="af979-115">Running the command ildasm.exe on the Hello.exe assembly and double-clicking the MANIFEST icon in the IL DASM window produces the following output:</span></span>  
  
```  
// Metadata version: v4.0.30319  
.assembly extern mscorlib  
{  
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..  
  .ver 4:0:0:0  
}  
.assembly Hello  
{  
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )   
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx  
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.  
  .hash algorithm 0x00008004  
  .ver 0:0:0:0  
}  
.module Hello.exe  
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}  
.imagebase 0x00400000  
.file alignment 0x00000200  
.stackreserve 0x00100000  
.subsystem 0x0003       // WINDOWS_CUI  
.corflags 0x00000001    //  ILONLY  
// Image base: 0x00600000  
```  
  
 <span data-ttu-id="af979-116">В следующей таблице описаны все директивы в манифесте сборки Hello.exe, используемой в этом примере.</span><span class="sxs-lookup"><span data-stu-id="af979-116">The following table describes each directive in the assembly manifest of the Hello.exe assembly used in the example.</span></span>  
  
|<span data-ttu-id="af979-117">Директива</span><span class="sxs-lookup"><span data-stu-id="af979-117">Directive</span></span>|<span data-ttu-id="af979-118">Описание</span><span class="sxs-lookup"><span data-stu-id="af979-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af979-119">**.assembly extern \<** *имя_сборки* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-119">**.assembly extern \<** *assembly name* **>**</span></span>|<span data-ttu-id="af979-120">Определяет другую сборку, содержащую элементы, на которые имеются ссылки в текущем модуле (в этом примере — `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="af979-120">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|  
|<span data-ttu-id="af979-121">**.publickeytoken \<** *маркер* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-121">**.publickeytoken \<** *token* **>**</span></span>|<span data-ttu-id="af979-122">Определяет маркер действующего ключа сборки, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="af979-122">Specifies the token of the actual key of the referenced assembly.</span></span>|  
|<span data-ttu-id="af979-123">**.ver \<** *номер_версии* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-123">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="af979-124">Задает номер версии, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="af979-124">Specifies the version number of the referenced assembly.</span></span>|  
|<span data-ttu-id="af979-125">**.assembly \<** *имя_сборки* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-125">**.assembly \<** *assembly name* **>**</span></span>|<span data-ttu-id="af979-126">Задает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="af979-126">Specifies the assembly name.</span></span>|  
|<span data-ttu-id="af979-127">**.hash algorithm \<** *значение_int32* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-127">**.hash algorithm \<** *int32 value* **>**</span></span>|<span data-ttu-id="af979-128">Задает используемый хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="af979-128">Specifies the hash algorithm used.</span></span>|  
|<span data-ttu-id="af979-129">**.ver \<** *номер_версии* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-129">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="af979-130">Задает номер версии сборки.</span><span class="sxs-lookup"><span data-stu-id="af979-130">Specifies the version number of the assembly.</span></span>|  
|<span data-ttu-id="af979-131">**.module \<** *имя_файла* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-131">**.module \<** *file name* **>**</span></span>|<span data-ttu-id="af979-132">Задает имена модулей, составляющих сборку.</span><span class="sxs-lookup"><span data-stu-id="af979-132">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="af979-133">В этом примере сборка состоит только из одного файла.</span><span class="sxs-lookup"><span data-stu-id="af979-133">In this example, the assembly consists of only one file.</span></span>|  
|<span data-ttu-id="af979-134">**.subsystem \<** *значение* **>**</span><span class="sxs-lookup"><span data-stu-id="af979-134">**.subsystem \<** *value* **>**</span></span>|<span data-ttu-id="af979-135">Указывает требуемую для программы среду приложения.</span><span class="sxs-lookup"><span data-stu-id="af979-135">Specifies the application environment required for the program.</span></span> <span data-ttu-id="af979-136">В этом примере значение "3" указывает на то, что выполняемый модуль запускается на консоли.</span><span class="sxs-lookup"><span data-stu-id="af979-136">In this example, the value 3 indicates that this executable is run from a console.</span></span>|  
|<span data-ttu-id="af979-137">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="af979-137">**.corflags**</span></span>|<span data-ttu-id="af979-138">В настоящее время представляет собой зарезервированное поле метаданных.</span><span class="sxs-lookup"><span data-stu-id="af979-138">Currently a reserved field in the metadata.</span></span>|  
  
 <span data-ttu-id="af979-139">Манифест сборки может содержать несколько различных директив, зависящих от содержимого сборки.</span><span class="sxs-lookup"><span data-stu-id="af979-139">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="af979-140">Расширенный список директив манифеста сборки содержится в документации ECMA, в том числе в частях "Раздел II. Определение метаданных и семантика" и "Раздел III. Набор инструкций CIL".</span><span class="sxs-lookup"><span data-stu-id="af979-140">For an extensive list of the directives in the assembly manifest, see the ECMA documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="af979-141">Документация доступна в Интернете; см. страницы [ECMAC# и стандарты Common Language Infrastructure](http://go.microsoft.com/fwlink/?LinkID=99212) на сайте MSDN и [Стандарт ECMA-335 — общеязыковая инфраструктура (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) на международном веб-сайте организации ECMA.</span><span class="sxs-lookup"><span data-stu-id="af979-141">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af979-142">См. также</span><span class="sxs-lookup"><span data-stu-id="af979-142">See Also</span></span>  
 <span data-ttu-id="af979-143">[Домены приложений и сборки](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346) </span><span class="sxs-lookup"><span data-stu-id="af979-143">[Application Domains and Assemblies](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346) </span></span>  
 <span data-ttu-id="af979-144">[Руководства по работе с доменами приложений и сборками](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="af979-144">[Application Domains and Assemblies How-to Topics](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md) </span></span>  
 [<span data-ttu-id="af979-145">Ildasm.exe (дизассемблер IL)</span><span class="sxs-lookup"><span data-stu-id="af979-145">Ildasm.exe (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)

