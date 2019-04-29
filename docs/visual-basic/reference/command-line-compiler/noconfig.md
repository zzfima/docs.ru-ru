---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: 44bc619c489fdff36f0b595f7d8934689b859adb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789029"
---
# <a name="-noconfig"></a><span data-ttu-id="e32bd-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="e32bd-102">-noconfig</span></span>
<span data-ttu-id="e32bd-103">Указывает, что компилятор не должен ссылаться автоматически часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки или импорта `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e32bd-103">Specifies that the compiler should not automatically reference the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e32bd-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="e32bd-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e32bd-105">Remarks</span></span>  
 <span data-ttu-id="e32bd-106">`-noconfig` Указывает компилятору не выполнять компиляцию с помощью файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="e32bd-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="e32bd-107">Файл Vbc.rsp ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки и импортируемые объекты `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e32bd-107">The Vbc.rsp file references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="e32bd-108">Компилятор неявно ссылается на сборку System.dll, если не `-nostdlib` параметра.</span><span class="sxs-lookup"><span data-stu-id="e32bd-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="e32bd-109">`-nostdlib` Параметр указывает компилятору не компилировать с Vbc.rsp или автоматически ссылаются на сборки System.dll.</span><span class="sxs-lookup"><span data-stu-id="e32bd-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e32bd-110">Всегда существуют ссылки на сборки библиотеки Mscorlib.dll и Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="e32bd-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="e32bd-111">Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, которые должны быть включены в каждую компиляцию Vbc.exe (за исключением при указании `-noconfig` параметр).</span><span class="sxs-lookup"><span data-stu-id="e32bd-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="e32bd-112">Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="e32bd-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="e32bd-113">Компилятор обрабатывает параметры, передаваемые `vbc` последней команды.</span><span class="sxs-lookup"><span data-stu-id="e32bd-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="e32bd-114">Таким образом любой параметр командной строки переопределяет значение аналогичного параметра в файл Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="e32bd-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e32bd-115">`-noconfig` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e32bd-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32bd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e32bd-116">See also</span></span>

- [<span data-ttu-id="e32bd-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e32bd-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="e32bd-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="e32bd-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e32bd-119">@ (указание файла ответов)</span><span class="sxs-lookup"><span data-stu-id="e32bd-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="e32bd-120">-ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e32bd-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
