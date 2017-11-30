---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6b5da8e5eacacde9de5bdc54ef2d5e4d7f0d2653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="rootnamespace"></a><span data-ttu-id="94494-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="94494-102">/rootnamespace</span></span>
<span data-ttu-id="94494-103">Задает пространство имен для всех объявлений типов.</span><span class="sxs-lookup"><span data-stu-id="94494-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94494-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94494-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="94494-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="94494-105">Arguments</span></span>  
  
|<span data-ttu-id="94494-106">Термин</span><span class="sxs-lookup"><span data-stu-id="94494-106">Term</span></span>|<span data-ttu-id="94494-107">Определение</span><span class="sxs-lookup"><span data-stu-id="94494-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="94494-108">Имя пространства имен, в котором находятся все объявления типов для текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="94494-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94494-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="94494-109">Remarks</span></span>  
 <span data-ttu-id="94494-110">При использовании исполняемого файла Visual Studio (Devenv.exe) для компиляции в проект, созданный в среде разработки Visual Studio, используйте `/rootnamespace` для указания значения <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="94494-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="94494-111">В разделе [командной строки devenv](/visualstudio/ide/reference/devenv-command-line-switches) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="94494-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="94494-112">Использовать CLR дизассемблер MSIL (`Ildasm.exe`) для просмотра имен пространств имен в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="94494-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="94494-113">Задание/RootNamespace в Visual Studio интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="94494-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="94494-114">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="94494-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="94494-115">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="94494-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="94494-116">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="94494-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="94494-117">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="94494-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="94494-118">3.  Измените значение в **корневое пространство имен** поле.</span><span class="sxs-lookup"><span data-stu-id="94494-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94494-119">Пример</span><span class="sxs-lookup"><span data-stu-id="94494-119">Example</span></span>  
 <span data-ttu-id="94494-120">Следующий код компилирует `In.vb` и помещает все объявления типов в пространстве имен `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="94494-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="94494-121">См. также</span><span class="sxs-lookup"><span data-stu-id="94494-121">See Also</span></span>  
 [<span data-ttu-id="94494-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="94494-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="94494-123">Ildasm.exe (дизассемблер IL)</span><span class="sxs-lookup"><span data-stu-id="94494-123">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="94494-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="94494-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
