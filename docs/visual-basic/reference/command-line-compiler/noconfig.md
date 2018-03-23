---
title: -noconfig
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2cebc617aea9ebbb16197f27841794b2e6ad46ea
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-noconfig"></a><span data-ttu-id="8b36f-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="8b36f-102">-noconfig</span></span>
<span data-ttu-id="8b36f-103">Указывает, что компилятор не должен ссылаться автоматически часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки или импорта `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8b36f-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b36f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b36f-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="8b36f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b36f-105">Remarks</span></span>  
 <span data-ttu-id="8b36f-106">`-noconfig` Параметр предписывает компилятору не компилировать с использованием файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="8b36f-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="8b36f-107">Файл Vbc.rsp ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8b36f-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="8b36f-108">Компилятор неявно ссылается на сборку System.dll, если не `-nostdlib` параметра.</span><span class="sxs-lookup"><span data-stu-id="8b36f-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="8b36f-109">`-nostdlib` Параметр предписывает компилятору не компилировать с Vbc.rsp или автоматически ссылку на сборку System.dll.</span><span class="sxs-lookup"><span data-stu-id="8b36f-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b36f-110">Всегда создаются ссылки на сборки Mscorlib.dll и Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="8b36f-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="8b36f-111">Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, должны быть включены в каждую компиляцию Vbc.exe (за исключением при указании `-noconfig` параметр).</span><span class="sxs-lookup"><span data-stu-id="8b36f-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="8b36f-112">Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="8b36f-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="8b36f-113">Компилятор обрабатывает параметры, передаваемые `vbc` последней команды.</span><span class="sxs-lookup"><span data-stu-id="8b36f-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="8b36f-114">Таким образом любой параметр командной строки переопределяет параметр того же параметра в файле Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="8b36f-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b36f-115">`-noconfig` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="8b36f-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b36f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8b36f-116">See Also</span></span>  
 [<span data-ttu-id="8b36f-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b36f-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [<span data-ttu-id="8b36f-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="8b36f-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8b36f-119">@ (указание файла ответов)</span><span class="sxs-lookup"><span data-stu-id="8b36f-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [<span data-ttu-id="8b36f-120">-ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b36f-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
