---
title: -addmodule (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: 148a63c37cfbc4c60448adccde10947e91e22bb9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970177"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="1034f-102">-addmodule (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="1034f-102">-addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="1034f-103">Установка этого параметра приводит к добавлению модуля, созданного с помощью параметра target:module для текущей компиляции.</span><span class="sxs-lookup"><span data-stu-id="1034f-103">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1034f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1034f-104">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1034f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1034f-105">Arguments</span></span>  
 <span data-ttu-id="1034f-106">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="1034f-106">`file`, `file2`</span></span>  
 <span data-ttu-id="1034f-107">Выходной файл, содержащий метаданные.</span><span class="sxs-lookup"><span data-stu-id="1034f-107">An output file that contains metadata.</span></span> <span data-ttu-id="1034f-108">В данный файл не может входить манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="1034f-108">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="1034f-109">Чтобы импортировать несколько файлов, разделите их имена запятыми или точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="1034f-109">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1034f-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="1034f-110">Remarks</span></span>  
 <span data-ttu-id="1034f-111">Все модули, добавленные с помощью **-addmodule**, во время выполнения должны находиться в том же каталоге, что и выходной файл.</span><span class="sxs-lookup"><span data-stu-id="1034f-111">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="1034f-112">То есть во время компиляции можно указать модуль в любом каталоге, но во время выполнения он должен находиться в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="1034f-112">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="1034f-113">Если во время выполнения модуль отсутствует в каталоге приложения, возникнет <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="1034f-113">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="1034f-114">`file` не может содержать сборку.</span><span class="sxs-lookup"><span data-stu-id="1034f-114">`file` cannot contain an assembly.</span></span> <span data-ttu-id="1034f-115">Например, если выходной файл был создан с помощью [-target:module](./target-module-compiler-option.md), для импорта его метаданных можно использовать **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="1034f-115">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="1034f-116">Если выходной файл был создан с помощью параметра **-target**, отличного от **-target:module**, для импорта его метаданных запрещено использовать **-addmodule**, но можно [-reference](./reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1034f-116">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="1034f-117">Этот параметр компилятора недоступен в Visual Studio; проект не может ссылаться на модуль.</span><span class="sxs-lookup"><span data-stu-id="1034f-117">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="1034f-118">Кроме того, этот параметр компилятора нельзя изменить программным способом.</span><span class="sxs-lookup"><span data-stu-id="1034f-118">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1034f-119">Пример</span><span class="sxs-lookup"><span data-stu-id="1034f-119">Example</span></span>  
 <span data-ttu-id="1034f-120">Скомпилируйте исходный файл `input.cs` и добавьте метаданные из `metad1.netmodule` и `metad2.netmodule`, чтобы создать `out.exe`.</span><span class="sxs-lookup"><span data-stu-id="1034f-120">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="1034f-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1034f-121">See also</span></span>

- [<span data-ttu-id="1034f-122">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="1034f-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="1034f-123">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="1034f-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="1034f-124">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="1034f-124">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="1034f-125">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="1034f-125">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
