---
title: "@ (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 219c12e4e3c9b847400f00a135d58506c72d2e7f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-c-compiler-options"></a><span data-ttu-id="34a70-102">@ (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="34a70-102">@ (C# Compiler Options)</span></span>
<span data-ttu-id="34a70-103">С помощью параметра @ можно указать файл, содержащий параметры компилятора и файлы исходного кода, которые требуется компилировать.</span><span class="sxs-lookup"><span data-stu-id="34a70-103">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34a70-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="34a70-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="34a70-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="34a70-106">Файл, содержащий параметры компилятора и файлы исходного кода, которые требуется компилировать.</span><span class="sxs-lookup"><span data-stu-id="34a70-106">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34a70-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="34a70-107">Remarks</span></span>  
 <span data-ttu-id="34a70-108">Параметры компилятора и файлы исходного кода будут обрабатываться компилятором таким образом, как если бы они были указаны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="34a70-108">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="34a70-109">Чтобы задать несколько файлов ответов для компиляции, используйте соответствующее число параметров файла ответов.</span><span class="sxs-lookup"><span data-stu-id="34a70-109">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="34a70-110">Например:</span><span class="sxs-lookup"><span data-stu-id="34a70-110">For example:</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="34a70-111">В одной строке файла ответов может содержаться несколько параметров компилятора и файлов исходного кода.</span><span class="sxs-lookup"><span data-stu-id="34a70-111">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="34a70-112">Спецификация отдельного параметра компилятора должна размещаться на одной строке и не может разбиваться на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="34a70-112">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="34a70-113">В файл ответов можно добавлять комментарии, которые должны начинаться с символа #.</span><span class="sxs-lookup"><span data-stu-id="34a70-113">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="34a70-114">Указание параметров компилятора в файле ответов аналогично выполнению соответствующих команд из командной строки.</span><span class="sxs-lookup"><span data-stu-id="34a70-114">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="34a70-115">Дополнительные сведения см. в разделе [Построение из командной строки](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="34a70-115">See [Building from the Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="34a70-116">Компилятор обрабатывает параметры команд в том порядке, в котором они встречаются.</span><span class="sxs-lookup"><span data-stu-id="34a70-116">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="34a70-117">Таким образом, аргументы командной строки могут переопределять параметры, заданные ранее в файле ответов.</span><span class="sxs-lookup"><span data-stu-id="34a70-117">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="34a70-118">Аналогичным образом, параметры в файле ответов будут переопределять параметры, ранее заданные в командной строке или в других файлах ответов.</span><span class="sxs-lookup"><span data-stu-id="34a70-118">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="34a70-119">В C# представлен файл csc.rsp, который находится в одном каталоге с файлом csc.exe.</span><span class="sxs-lookup"><span data-stu-id="34a70-119">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="34a70-120">Дополнительные сведения о файле csc.rsp см. в разделе [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="34a70-120">See [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="34a70-121">Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.</span><span class="sxs-lookup"><span data-stu-id="34a70-121">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a70-122">Пример</span><span class="sxs-lookup"><span data-stu-id="34a70-122">Example</span></span>  
 <span data-ttu-id="34a70-123">Ниже приведено несколько строк из образца файла ответов:</span><span class="sxs-lookup"><span data-stu-id="34a70-123">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="34a70-124">См. также</span><span class="sxs-lookup"><span data-stu-id="34a70-124">See Also</span></span>  
 [<span data-ttu-id="34a70-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="34a70-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

