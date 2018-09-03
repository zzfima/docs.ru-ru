---
title: -pathmap (параметры компилятора C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 277ab8e094f28fd5e3cbba4de12e742bb9614730
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43475924"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="aed07-102">-pathmap (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="aed07-102">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="aed07-103">Параметр компилятора **-pathmap** определяет способ сопоставления физических путей и выходных имен исходных путей компилятором.</span><span class="sxs-lookup"><span data-stu-id="aed07-103">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="aed07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aed07-104">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="aed07-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="aed07-105">Arguments</span></span>

 <span data-ttu-id="aed07-106">`path1` — полный путь к исходным файлам в текущем окружении.</span><span class="sxs-lookup"><span data-stu-id="aed07-106">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="aed07-107">`sourcePath1` — исходный путь подставляется вместо `path1` в любых выходных файлах.</span><span class="sxs-lookup"><span data-stu-id="aed07-107">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="aed07-108">Чтобы указать несколько сопоставленных исходных путей, разделите их запятыми.</span><span class="sxs-lookup"><span data-stu-id="aed07-108">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="aed07-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="aed07-109">Remarks</span></span>

<span data-ttu-id="aed07-110">Компилятор записывает исходный путь в выходные данные по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="aed07-110">The compiler writes the source path path into its output for the following reasons:</span></span>

1. <span data-ttu-id="aed07-111">Исходный путь подставляется вместо аргумента, когда <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> применяется как необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aed07-111">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="aed07-112">Исходный путь внедряется как PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="aed07-112">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="aed07-113">Путь к PDB-файлу внедряется в PE-файл (переносимый исполняемый файл).</span><span class="sxs-lookup"><span data-stu-id="aed07-113">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="aed07-114">Этот параметр сопоставляет каждый физический путь на компьютере, где выполняется компилятор, с соответствующим путем, который должен быть записан в выходные файлы.</span><span class="sxs-lookup"><span data-stu-id="aed07-114">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="aed07-115">Пример</span><span class="sxs-lookup"><span data-stu-id="aed07-115">Example</span></span>

<span data-ttu-id="aed07-116">Компиляция `t.cs` в каталоге **C:\\work\\tests** и сопоставление этого каталога с каталогом **\publish** в выходных данных:</span><span class="sxs-lookup"><span data-stu-id="aed07-116">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="aed07-117">См. также</span><span class="sxs-lookup"><span data-stu-id="aed07-117">See also</span></span>

- [<span data-ttu-id="aed07-118">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="aed07-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="aed07-119">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="aed07-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
