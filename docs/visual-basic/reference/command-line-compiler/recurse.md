---
title: -recurse
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 195d4b8f8e88d22e63c29ab9152399eb5c4a19df
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="-recurse"></a><span data-ttu-id="be2c1-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="be2c1-102">-recurse</span></span>
<span data-ttu-id="be2c1-103">Компилирует файлы с исходным кодом во всех дочерних папках указанного каталога или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="be2c1-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be2c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be2c1-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="be2c1-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="be2c1-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="be2c1-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="be2c1-106">Optional.</span></span> <span data-ttu-id="be2c1-107">Каталог, с которого будет начинаться поиск.</span><span class="sxs-lookup"><span data-stu-id="be2c1-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="be2c1-108">Если не указан, поиск начинается в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="be2c1-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="be2c1-109">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="be2c1-109">Required.</span></span> <span data-ttu-id="be2c1-110">Файлы для поиска.</span><span class="sxs-lookup"><span data-stu-id="be2c1-110">The file(s) to search for.</span></span> <span data-ttu-id="be2c1-111">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="be2c1-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be2c1-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="be2c1-112">Remarks</span></span>  
 <span data-ttu-id="be2c1-113">Можно использовать подстановочные знаки в имени файла для компиляции всех файлов в каталоге проекта без использования `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="be2c1-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="be2c1-114">Если указано имя выходного файла, компилятор использует имя выходного файла, обработано первой входной файл.</span><span class="sxs-lookup"><span data-stu-id="be2c1-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="be2c1-115">Обычно это первый файл в списке файлов, скомпилированных в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="be2c1-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="be2c1-116">По этой причине лучше всего задать выходной файл с помощью `-out` параметр.</span><span class="sxs-lookup"><span data-stu-id="be2c1-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be2c1-117">`-recurse` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="be2c1-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be2c1-118">Пример</span><span class="sxs-lookup"><span data-stu-id="be2c1-118">Example</span></span>  
 <span data-ttu-id="be2c1-119">Следующая команда компилирует все файлы Visual Basic в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="be2c1-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="be2c1-120">Следующая команда компилирует все файлы Visual Basic в `Test\ABC` каталога и любые каталоги под ним, а затем создает `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="be2c1-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="be2c1-121">См. также</span><span class="sxs-lookup"><span data-stu-id="be2c1-121">See Also</span></span>  
 [<span data-ttu-id="be2c1-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="be2c1-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="be2c1-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be2c1-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)  
 [<span data-ttu-id="be2c1-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="be2c1-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
