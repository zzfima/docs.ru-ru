---
title: '@ (указание файла ответа) (Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 6b993a6399eec4e203821109db153aadf246cbac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838122"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="52c80-102">@ (указание файла ответа) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52c80-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="52c80-103">Указывает файл, содержащий параметры компилятора и файлы исходного кода для компиляции.</span><span class="sxs-lookup"><span data-stu-id="52c80-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52c80-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="52c80-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="52c80-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="52c80-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="52c80-106">Required.</span></span> <span data-ttu-id="52c80-107">Файл, содержащий параметры компилятора и файлы исходного кода для компиляции.</span><span class="sxs-lookup"><span data-stu-id="52c80-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="52c80-108">Заключите имя файла в кавычки (» «), если он содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="52c80-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52c80-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="52c80-109">Remarks</span></span>  
 <span data-ttu-id="52c80-110">Компилятор обрабатывает параметры компилятора и файлы исходного кода, указанный в файле ответов, как если бы они были указаны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="52c80-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="52c80-111">Чтобы указать более одного файла ответов при компиляции, укажите несколько вариантов файл ответов, например следующие.</span><span class="sxs-lookup"><span data-stu-id="52c80-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="52c80-112">В ответ на одной строке можно указать файл, несколько параметры компилятора и файлов исходного кода.</span><span class="sxs-lookup"><span data-stu-id="52c80-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="52c80-113">Параметр компилятора должен записываться в одной строке (не может занимать несколько строк).</span><span class="sxs-lookup"><span data-stu-id="52c80-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="52c80-114">Файл ответов можно добавлять комментарии, начинающиеся с `#` символов.</span><span class="sxs-lookup"><span data-stu-id="52c80-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="52c80-115">Можно комбинировать параметры, указанные в командной строке параметры из одного или нескольких файлов ответа.</span><span class="sxs-lookup"><span data-stu-id="52c80-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="52c80-116">Компилятор обрабатывает параметры команд, они встречаются.</span><span class="sxs-lookup"><span data-stu-id="52c80-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="52c80-117">Таким образом аргументы командной строки могут переопределять параметры, указанные в файлах ответов.</span><span class="sxs-lookup"><span data-stu-id="52c80-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="52c80-118">И наоборот параметры в файл ответов переопределять ранее указанные параметры в командной строке или в других файлах ответов.</span><span class="sxs-lookup"><span data-stu-id="52c80-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="52c80-119">Visual Basic предоставляет файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="52c80-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="52c80-120">Файл Vbc.rsp включается по умолчанию, если не `-noconfig` используется параметр.</span><span class="sxs-lookup"><span data-stu-id="52c80-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="52c80-121">Дополнительные сведения см. в разделе [- noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="52c80-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52c80-122">`@` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="52c80-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52c80-123">Пример</span><span class="sxs-lookup"><span data-stu-id="52c80-123">Example</span></span>  
 <span data-ttu-id="52c80-124">Приведенный ниже взяты из образца файла ответов.</span><span class="sxs-lookup"><span data-stu-id="52c80-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="52c80-125">Пример</span><span class="sxs-lookup"><span data-stu-id="52c80-125">Example</span></span>  
 <span data-ttu-id="52c80-126">Следующий пример демонстрирует, как использовать `@` параметр ответа-файл с именем `File1.rsp`.</span><span class="sxs-lookup"><span data-stu-id="52c80-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="52c80-127">См. также</span><span class="sxs-lookup"><span data-stu-id="52c80-127">See also</span></span>

- [<span data-ttu-id="52c80-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="52c80-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="52c80-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="52c80-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="52c80-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="52c80-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
