---
title: "-doc (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c668c79ca2c68d1a497521581857085e57c71f5c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-doc-c-compiler-options"></a><span data-ttu-id="31abe-102">-doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="31abe-102">-doc (C# Compiler Options)</span></span>
<span data-ttu-id="31abe-103">Параметр **-doc** позволяет поместить комментарии документации в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="31abe-103">The **-doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31abe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31abe-104">Syntax</span></span>  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="31abe-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="31abe-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="31abe-106">Выходной XML-файл, который заполняется комментариями из файлов исходного кода, участвующих в компиляции.</span><span class="sxs-lookup"><span data-stu-id="31abe-106">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31abe-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="31abe-107">Remarks</span></span>  
 <span data-ttu-id="31abe-108">Комментарии документации могут быть обработаны и добавлены в XML-файл, если они предшествуют объектам файлов исходного кода, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="31abe-108">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
-   <span data-ttu-id="31abe-109">Такие определяемые пользователем типы, как [класс](../../../csharp/language-reference/keywords/class.md), [делегат](../../../csharp/language-reference/keywords/delegate.md) или [интерфейс](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="31abe-109">Such user-defined types as a [class](../../../csharp/language-reference/keywords/class.md), [delegate](../../../csharp/language-reference/keywords/delegate.md), or [interface](../../../csharp/language-reference/keywords/interface.md)</span></span>  
  
-   <span data-ttu-id="31abe-110">Такие члены, как поле, [событие](../../../csharp/language-reference/keywords/event.md), [свойство](../../../csharp/programming-guide/classes-and-structs/using-properties.md) или метод.</span><span class="sxs-lookup"><span data-stu-id="31abe-110">Such members as a field, [event](../../../csharp/language-reference/keywords/event.md), [property](../../../csharp/programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="31abe-111">Файл исходного кода, содержащий метод "Main", первым выводится в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="31abe-111">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="31abe-112">Чтобы использовать созданный XML-файл с помощью функции [IntelliSense](/visualstudio/ide/using-intellisense), имя XML-файла должно совпадать с именем сборки, а сам XML-файл должен находиться в одном каталоге со сборкой.</span><span class="sxs-lookup"><span data-stu-id="31abe-112">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="31abe-113">Таким образом, если в проект Visual Studio добавляется ссылка на сборку, то XML-файл также будет найден.</span><span class="sxs-lookup"><span data-stu-id="31abe-113">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="31abe-114">Дополнительные сведения см. в разделе [Создание XML-примечаний к коду](/visualstudio/ide/supplying-xml-code-comments).</span><span class="sxs-lookup"><span data-stu-id="31abe-114">See [Supplying Code Comments](/visualstudio/ide/supplying-xml-code-comments) and for more information.</span></span>  
  
 <span data-ttu-id="31abe-115">Если при компиляции не используется параметр [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), `file` будет содержать теги \<assembly>\</assembly>, которые указывают имя файла, содержащего манифест сборки для выходного файла компиляции.</span><span class="sxs-lookup"><span data-stu-id="31abe-115">Unless you compile with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31abe-116">Параметр -doc применяется ко всем входным файлам или (если он установлен в параметрах проекта) ко всем файлам проекта.</span><span class="sxs-lookup"><span data-stu-id="31abe-116">The -doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="31abe-117">Чтобы отключить предупреждения, связанные с комментариями документации для определенного файла или раздела кода, используйте директиву [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="31abe-117">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="31abe-118">Способы создания документации из комментариев в коде описаны в разделе [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).</span><span class="sxs-lookup"><span data-stu-id="31abe-118">See [Recommended Tags for Documentation Comments](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="31abe-119">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31abe-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="31abe-120">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="31abe-120">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="31abe-121">Перейдите на вкладку **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="31abe-121">Click the **Build** tab.</span></span>  
  
3.  <span data-ttu-id="31abe-122">Измените свойство **XML-файл документации**.</span><span class="sxs-lookup"><span data-stu-id="31abe-122">Modify the **XML documentation file** property.</span></span>  
  
 <span data-ttu-id="31abe-123">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="31abe-123">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31abe-124">См. также</span><span class="sxs-lookup"><span data-stu-id="31abe-124">See Also</span></span>  
 [<span data-ttu-id="31abe-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="31abe-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="31abe-126">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="31abe-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
