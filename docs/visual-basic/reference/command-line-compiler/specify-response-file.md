---
title: '@ (указание файла ответа) (Visual Basic)'
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af66000208dee0896792892a52dc6acdf5cb1e37
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="d5a52-102">@ (указание файла ответа) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5a52-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="d5a52-103">Указывает файл, содержащий параметры компилятора и файлы исходного кода для компиляции.</span><span class="sxs-lookup"><span data-stu-id="d5a52-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5a52-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d5a52-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d5a52-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="d5a52-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="d5a52-106">Required.</span></span> <span data-ttu-id="d5a52-107">Файл, содержащий параметры компилятора и файлы исходного кода для компиляции.</span><span class="sxs-lookup"><span data-stu-id="d5a52-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="d5a52-108">Заключите имя файла в кавычки (» «), если он содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="d5a52-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5a52-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5a52-109">Remarks</span></span>  
 <span data-ttu-id="d5a52-110">Компилятор обрабатывает параметры компилятора и файлы исходного кода, указанного в файле ответов, как если бы они были указаны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="d5a52-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="d5a52-111">Чтобы указать более одного файла ответов при компиляции, укажите несколько параметров файла ответов, следующие.</span><span class="sxs-lookup"><span data-stu-id="d5a52-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="d5a52-112">В ответ на несколько файлов, параметров компилятора и файлов исходного кода могут отображаться на одной строке.</span><span class="sxs-lookup"><span data-stu-id="d5a52-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="d5a52-113">Каждый параметр компилятора должен записываться в одной строке (не может занимать несколько строк).</span><span class="sxs-lookup"><span data-stu-id="d5a52-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="d5a52-114">Файл ответов можно включать комментарии, которые начинаются с `#` символов.</span><span class="sxs-lookup"><span data-stu-id="d5a52-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="d5a52-115">Можно комбинировать параметры, указанные в командной строке с параметрами, заданными в один или несколько файлов ответов.</span><span class="sxs-lookup"><span data-stu-id="d5a52-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="d5a52-116">Компилятор обрабатывает параметры командной строки, они встречаются.</span><span class="sxs-lookup"><span data-stu-id="d5a52-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="d5a52-117">Таким образом аргументы командной строки могут переопределять параметры, указанные в файле ответа.</span><span class="sxs-lookup"><span data-stu-id="d5a52-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="d5a52-118">Таким же образом параметры в файле ответов переопределять ранее указанные параметры в командной строке или в других файлов ответов.</span><span class="sxs-lookup"><span data-stu-id="d5a52-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="d5a52-119">В Visual Basic предусмотрен файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="d5a52-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="d5a52-120">Файл Vbc.rsp включается по умолчанию, если не `-noconfig` используется параметр.</span><span class="sxs-lookup"><span data-stu-id="d5a52-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="d5a52-121">Дополнительные сведения см. в разделе [- noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="d5a52-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5a52-122">`@` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d5a52-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5a52-123">Пример</span><span class="sxs-lookup"><span data-stu-id="d5a52-123">Example</span></span>  
 <span data-ttu-id="d5a52-124">Следующие строки являются из образца файла ответов.</span><span class="sxs-lookup"><span data-stu-id="d5a52-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="d5a52-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d5a52-125">Example</span></span>  
 <span data-ttu-id="d5a52-126">В следующем примере демонстрируется использование `@` параметр с именем файла ответов `File1.rsp`.</span><span class="sxs-lookup"><span data-stu-id="d5a52-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5a52-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d5a52-127">See Also</span></span>  
 [<span data-ttu-id="d5a52-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d5a52-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d5a52-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="d5a52-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="d5a52-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d5a52-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
