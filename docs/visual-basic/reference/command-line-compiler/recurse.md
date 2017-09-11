---
title: "/ recurse | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9ceb2f3bc9e4d0f1088258f504b7a49c58a29e35
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="recurse"></a><span data-ttu-id="8a85f-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="8a85f-102">/recurse</span></span>
<span data-ttu-id="8a85f-103">Компилирует файлы исходного кода во всех дочерних каталогах в указанном каталоге или каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="8a85f-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a85f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a85f-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a85f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8a85f-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="8a85f-106">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8a85f-106">Optional.</span></span> <span data-ttu-id="8a85f-107">Каталог, в котором следует начать поиск.</span><span class="sxs-lookup"><span data-stu-id="8a85f-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="8a85f-108">Если не указан, поиск начинается в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="8a85f-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="8a85f-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8a85f-109">Required.</span></span> <span data-ttu-id="8a85f-110">Файлы для поиска.</span><span class="sxs-lookup"><span data-stu-id="8a85f-110">The file(s) to search for.</span></span> <span data-ttu-id="8a85f-111">Допускаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8a85f-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a85f-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a85f-112">Remarks</span></span>  
 <span data-ttu-id="8a85f-113">Можно использовать подстановочные знаки в имени файла для компиляции всех файлов из папки проекта без использования `/recurse`.</span><span class="sxs-lookup"><span data-stu-id="8a85f-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="8a85f-114">Если указано имя выходного файла, компилятор использует имя первого входного файла обработки.</span><span class="sxs-lookup"><span data-stu-id="8a85f-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="8a85f-115">Обычно это первый файл в списке файлов, скомпилированных в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="8a85f-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="8a85f-116">По этой причине лучше всего задать выходной файл с помощью `/out` параметр.</span><span class="sxs-lookup"><span data-stu-id="8a85f-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a85f-117">`/recurse` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="8a85f-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a85f-118">Пример</span><span class="sxs-lookup"><span data-stu-id="8a85f-118">Example</span></span>  
 <span data-ttu-id="8a85f-119">Следующий код компилирует все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8a85f-119">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="8a85f-120">Следующий код компилирует все [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлы в `Test\ABC` каталога и любые каталогов ниже его и затем создает `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="8a85f-120">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a85f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8a85f-121">See Also</span></span>  
 <span data-ttu-id="8a85f-122">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a85f-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8a85f-123"> [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span><span class="sxs-lookup"><span data-stu-id="8a85f-123"> [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span></span>  
<span data-ttu-id="8a85f-124"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="8a85f-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
