---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2fe1834c3e92c3eff016ffd7857a0473eb2e8b3a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816425"
---
# <a name="-recurse"></a><span data-ttu-id="5ce78-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="5ce78-102">-recurse</span></span>
<span data-ttu-id="5ce78-103">Компиляция файлов исходного кода во всех вложенных каталогах указанной папки или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="5ce78-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ce78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ce78-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="5ce78-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="5ce78-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="5ce78-106">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="5ce78-106">Optional.</span></span> <span data-ttu-id="5ce78-107">Каталог, с которого будет начинаться поиск.</span><span class="sxs-lookup"><span data-stu-id="5ce78-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="5ce78-108">Если не указан, поиск начинается в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="5ce78-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="5ce78-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5ce78-109">Required.</span></span> <span data-ttu-id="5ce78-110">Файлы для поиска.</span><span class="sxs-lookup"><span data-stu-id="5ce78-110">The file(s) to search for.</span></span> <span data-ttu-id="5ce78-111">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5ce78-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ce78-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ce78-112">Remarks</span></span>  
 <span data-ttu-id="5ce78-113">Можно использовать подстановочные знаки в имени файла, чтобы скомпилировать все соответствующие файлы в каталоге проекта без использования `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="5ce78-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="5ce78-114">Если указано имя выходного файла, компилятор использует имя выходного файла на обработки первого входного файла.</span><span class="sxs-lookup"><span data-stu-id="5ce78-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="5ce78-115">Обычно это первый файл в список скомпилированных файлов в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="5ce78-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="5ce78-116">По этой причине лучше всего указать выходной файл с помощью `-out` параметр.</span><span class="sxs-lookup"><span data-stu-id="5ce78-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ce78-117">`-recurse` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="5ce78-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ce78-118">Пример</span><span class="sxs-lookup"><span data-stu-id="5ce78-118">Example</span></span>  
 <span data-ttu-id="5ce78-119">Следующая команда компилирует все файлы Visual Basic в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5ce78-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="5ce78-120">Следующая команда компилирует все файлы Visual Basic в `Test\ABC` directory и каталогов под ним, а затем создает `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="5ce78-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ce78-121">См. также</span><span class="sxs-lookup"><span data-stu-id="5ce78-121">See also</span></span>

- [<span data-ttu-id="5ce78-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="5ce78-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5ce78-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ce78-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="5ce78-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="5ce78-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
