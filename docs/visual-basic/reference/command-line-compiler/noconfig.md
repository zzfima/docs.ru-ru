---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964396"
---
# <a name="-noconfig"></a><span data-ttu-id="55b46-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="55b46-102">-noconfig</span></span>
<span data-ttu-id="55b46-103">Указывает, что компилятор не должен автоматически ссылаться на часто используемые .NET Framework сборки или импортировать `System` пространства имен и. `Microsoft.VisualBasic`</span><span class="sxs-lookup"><span data-stu-id="55b46-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55b46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55b46-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="55b46-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="55b46-105">Remarks</span></span>  
 <span data-ttu-id="55b46-106">`-noconfig` Параметр указывает компилятору не компилировать файл Vbc. rsp, который находится в том же каталоге, что и файл Vbc. exe.</span><span class="sxs-lookup"><span data-stu-id="55b46-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="55b46-107">Файл Vbc. rsp ссылается на часто используемые сборки .NET Framework и импортирует `System` пространства имен и. `Microsoft.VisualBasic`</span><span class="sxs-lookup"><span data-stu-id="55b46-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="55b46-108">Компилятор неявно ссылается на сборку System. dll, `-nostdlib` если не указан параметр.</span><span class="sxs-lookup"><span data-stu-id="55b46-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="55b46-109">`-nostdlib` Параметр указывает компилятору не компилировать с Vbc. rsp или автоматически ссылаться на сборку System. dll.</span><span class="sxs-lookup"><span data-stu-id="55b46-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55b46-110">Ссылки на сборки mscorlib. dll и Microsoft. VisualBasic. dll всегда существуют.</span><span class="sxs-lookup"><span data-stu-id="55b46-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="55b46-111">Можно изменить файл Vbc. rsp, указав дополнительные параметры компилятора, которые должны включаться в каждую компиляцию Vbc. exe (за исключением случаев, `-noconfig` когда указан параметр).</span><span class="sxs-lookup"><span data-stu-id="55b46-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="55b46-112">Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="55b46-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="55b46-113">Компилятор обрабатывает параметры, переданные в `vbc` команду последними.</span><span class="sxs-lookup"><span data-stu-id="55b46-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="55b46-114">Таким образом, любой параметр в командной строке переопределяет параметр того же параметра в файле Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="55b46-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55b46-115">Этот `-noconfig` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="55b46-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b46-116">См. также</span><span class="sxs-lookup"><span data-stu-id="55b46-116">See also</span></span>

- [<span data-ttu-id="55b46-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55b46-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="55b46-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="55b46-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="55b46-119">@ (указание файла ответов)</span><span class="sxs-lookup"><span data-stu-id="55b46-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="55b46-120">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55b46-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
