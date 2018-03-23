---
title: -addmodule
ms.date: 03/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c17d5541fe2d02ba88f4c5ef259b2248f371dfe5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-addmodule"></a><span data-ttu-id="68fd4-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="68fd4-102">-addmodule</span></span>
<span data-ttu-id="68fd4-103">Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.</span><span class="sxs-lookup"><span data-stu-id="68fd4-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68fd4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68fd4-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="68fd4-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="68fd4-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="68fd4-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="68fd4-106">Required.</span></span> <span data-ttu-id="68fd4-107">Разделенный запятыми список файлов, которые содержат метаданные, но не содержат манифестов сборки.</span><span class="sxs-lookup"><span data-stu-id="68fd4-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="68fd4-108">Имена файлов, содержащие пробелы, которые должны быть заключены в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="68fd4-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68fd4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="68fd4-109">Remarks</span></span>  
 <span data-ttu-id="68fd4-110">Файлы, перечисленные по `fileList` параметр должен быть создан с `-target:module` параметр, или с помощью другого компилятора эквивалентно `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="68fd4-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="68fd4-111">Все модули, добавленные с `-addmodule` должно быть в том же каталоге, как выходного файла во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="68fd4-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="68fd4-112">То есть можно указать модуль в любом каталоге во время компиляции, но во время выполнения он должен находиться в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="68fd4-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="68fd4-113">Если это не так, вы получаете <xref:System.TypeLoadException> ошибки.</span><span class="sxs-lookup"><span data-stu-id="68fd4-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="68fd4-114">При указании (явно или неявно) любой[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) параметр, отличный от `-target:module` с `-addmodule`, передаются файлы `-addmodule` становятся частью сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="68fd4-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="68fd4-115">Сборки, необходимые для выполнения выходного файла, который имеет один или несколько файлов добавлены, `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="68fd4-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="68fd4-116">Используйте [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.</span><span class="sxs-lookup"><span data-stu-id="68fd4-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68fd4-117">`-addmodule` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="68fd4-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68fd4-118">Пример</span><span class="sxs-lookup"><span data-stu-id="68fd4-118">Example</span></span>  
 <span data-ttu-id="68fd4-119">В следующем коде создается модуль.</span><span class="sxs-lookup"><span data-stu-id="68fd4-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 <span data-ttu-id="68fd4-120">Следующий код импортирует типы модуля.</span><span class="sxs-lookup"><span data-stu-id="68fd4-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 <span data-ttu-id="68fd4-121">При запуске `t1`, он выводит `802`.</span><span class="sxs-lookup"><span data-stu-id="68fd4-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fd4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="68fd4-122">See Also</span></span>  
 [<span data-ttu-id="68fd4-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="68fd4-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="68fd4-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68fd4-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="68fd4-125">-ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68fd4-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="68fd4-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="68fd4-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
