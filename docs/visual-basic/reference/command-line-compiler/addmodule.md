---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 0e0915a2534f950cec074632a59750c3f96b679d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962457"
---
# <a name="-addmodule"></a><span data-ttu-id="32525-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="32525-102">-addmodule</span></span>
<span data-ttu-id="32525-103">Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.</span><span class="sxs-lookup"><span data-stu-id="32525-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32525-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32525-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="32525-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="32525-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="32525-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="32525-106">Required.</span></span> <span data-ttu-id="32525-107">Разделенный запятыми список файлов, содержащих метаданные, но не содержащих Манифесты сборки.</span><span class="sxs-lookup"><span data-stu-id="32525-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="32525-108">Имена файлов, содержащие пробелы, должны быть заключены в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="32525-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32525-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="32525-109">Remarks</span></span>  
 <span data-ttu-id="32525-110">Файлы, перечисленные в `fileList` параметре, должны быть созданы `-target:module` с параметром или с `-target:module`другим эквивалентом компилятора.</span><span class="sxs-lookup"><span data-stu-id="32525-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="32525-111">Все модули, добавленные с помощью `-addmodule` , должны находиться в одном каталоге с выходным файлом во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="32525-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="32525-112">Это значит, что модуль можно указать в любом каталоге во время компиляции, но во время выполнения модуль должен находиться в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="32525-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="32525-113">Если это не так, <xref:System.TypeLoadException> возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="32525-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="32525-114">При указании (неявно или явно) любого[целевого параметра (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) `-addmodule`, отличного от `-target:module` , передаваемые `-addmodule` файлы становятся частью сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="32525-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="32525-115">Сборка необходима для запуска выходного файла, который содержит один или несколько файлов, добавленных `-addmodule`с помощью.</span><span class="sxs-lookup"><span data-stu-id="32525-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="32525-116">Используйте [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.</span><span class="sxs-lookup"><span data-stu-id="32525-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="32525-117">Этот `-addmodule` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="32525-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32525-118">Пример</span><span class="sxs-lookup"><span data-stu-id="32525-118">Example</span></span>  
 <span data-ttu-id="32525-119">Следующий код создает модуль.</span><span class="sxs-lookup"><span data-stu-id="32525-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="32525-120">Следующий код импортирует типы модуля.</span><span class="sxs-lookup"><span data-stu-id="32525-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="32525-121">При запуске `t1`он выводит `802`.</span><span class="sxs-lookup"><span data-stu-id="32525-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32525-122">См. также</span><span class="sxs-lookup"><span data-stu-id="32525-122">See also</span></span>

- [<span data-ttu-id="32525-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="32525-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="32525-124">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32525-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="32525-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32525-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="32525-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="32525-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
