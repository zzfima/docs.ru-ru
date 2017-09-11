---
title: "/ noconfig | Документы Microsoft"
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
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
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
ms.openlocfilehash: fe3271e4a119e0c40370a7351bb39188f4d1c8ef
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="noconfig"></a><span data-ttu-id="e17dc-102">/noconfig</span><span class="sxs-lookup"><span data-stu-id="e17dc-102">/noconfig</span></span>
<span data-ttu-id="e17dc-103">Указывает, что компилятор не должен ссылаться автоматически часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки или импорт `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e17dc-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e17dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e17dc-104">Syntax</span></span>  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="e17dc-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e17dc-105">Remarks</span></span>  
 <span data-ttu-id="e17dc-106">`/noconfig` Параметр указывает компилятору не компилировать с использованием файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="e17dc-106">The `/noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="e17dc-107">Файл Vbc.rsp ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e17dc-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="e17dc-108">Компилятор неявно ссылается на сборку System.dll, если `/nostdlib` параметра.</span><span class="sxs-lookup"><span data-stu-id="e17dc-108">The compiler implicitly references the System.dll assembly unless the `/nostdlib` option is specified.</span></span> <span data-ttu-id="e17dc-109">`/nostdlib` Параметр указывает компилятору не компилировать с Vbc или автоматически ссылаться на сборки System.dll.</span><span class="sxs-lookup"><span data-stu-id="e17dc-109">The `/nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e17dc-110">Сборки Mscorlib.dll и Microsoft.VisualBasic.dll всегда имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="e17dc-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="e17dc-111">Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, должны быть включены в каждую компиляцию Vbc.exe (за исключением при указании `/noconfig` параметр).</span><span class="sxs-lookup"><span data-stu-id="e17dc-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `/noconfig` option).</span></span> <span data-ttu-id="e17dc-112">Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="e17dc-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="e17dc-113">Компилятор обрабатывает параметры, передаваемые `vbc` последней команды.</span><span class="sxs-lookup"><span data-stu-id="e17dc-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="e17dc-114">Таким образом любой параметр в командной строке переопределяет настройки того же параметра в файле Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="e17dc-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e17dc-115">`/noconfig` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e17dc-115">The `/noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e17dc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e17dc-116">See Also</span></span>  
 <span data-ttu-id="e17dc-117">[/ nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span><span class="sxs-lookup"><span data-stu-id="e17dc-117">[/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md) </span></span>  
<span data-ttu-id="e17dc-118"> [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="e17dc-118"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="e17dc-119"> [@ (Указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span><span class="sxs-lookup"><span data-stu-id="e17dc-119"> [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) </span></span>  
<span data-ttu-id="e17dc-120"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span><span class="sxs-lookup"><span data-stu-id="e17dc-120"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)</span></span>
