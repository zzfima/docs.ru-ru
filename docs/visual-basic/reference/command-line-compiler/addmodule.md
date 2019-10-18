---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524476"
---
# <a name="-addmodule"></a><span data-ttu-id="f1573-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="f1573-102">-addmodule</span></span>
<span data-ttu-id="f1573-103">Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.</span><span class="sxs-lookup"><span data-stu-id="f1573-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1573-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1573-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f1573-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f1573-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="f1573-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f1573-106">Required.</span></span> <span data-ttu-id="f1573-107">Разделенный запятыми список файлов, содержащих метаданные, но не содержащих Манифесты сборки.</span><span class="sxs-lookup"><span data-stu-id="f1573-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="f1573-108">Имена файлов, содержащие пробелы, должны быть заключены в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="f1573-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1573-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="f1573-109">Remarks</span></span>  
 <span data-ttu-id="f1573-110">Файлы, перечисленные в параметре `fileList`, необходимо создать с параметром `-target:module` или с помощью другого компилятора, эквивалентного `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="f1573-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="f1573-111">Все модули, добавленные с `-addmodule`, должны находиться в одном каталоге с выходным файлом во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f1573-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="f1573-112">Это значит, что модуль можно указать в любом каталоге во время компиляции, но во время выполнения модуль должен находиться в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="f1573-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="f1573-113">Если это не так, возникает ошибка <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="f1573-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="f1573-114">При указании (неявно или явно) любого[целевого параметра (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) , кроме `-target:module` с `-addmodule`, файлы, передаваемые `-addmodule`, становятся частью сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="f1573-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="f1573-115">Сборка необходима для запуска выходного файла, который содержит один или несколько файлов, добавленных с помощью `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="f1573-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="f1573-116">Используйте [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.</span><span class="sxs-lookup"><span data-stu-id="f1573-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1573-117">Параметр `-addmodule` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f1573-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1573-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f1573-118">Example</span></span>  
 <span data-ttu-id="f1573-119">Следующий код создает модуль.</span><span class="sxs-lookup"><span data-stu-id="f1573-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="f1573-120">Следующий код импортирует типы модуля.</span><span class="sxs-lookup"><span data-stu-id="f1573-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="f1573-121">При запуске `t1` выводит `802`.</span><span class="sxs-lookup"><span data-stu-id="f1573-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1573-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f1573-122">See also</span></span>

- [<span data-ttu-id="f1573-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="f1573-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f1573-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1573-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="f1573-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1573-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="f1573-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="f1573-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
