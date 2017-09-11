---
title: "/ rootnamespace | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
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
ms.openlocfilehash: 9a7a26407e981d3aea58d970d88bf25025e6bba6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="rootnamespace"></a><span data-ttu-id="4dd58-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="4dd58-102">/rootnamespace</span></span>
<span data-ttu-id="4dd58-103">Задает пространство имен для всех объявлений типов.</span><span class="sxs-lookup"><span data-stu-id="4dd58-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dd58-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4dd58-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="4dd58-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4dd58-105">Arguments</span></span>  
  
|<span data-ttu-id="4dd58-106">Термин</span><span class="sxs-lookup"><span data-stu-id="4dd58-106">Term</span></span>|<span data-ttu-id="4dd58-107">Определение</span><span class="sxs-lookup"><span data-stu-id="4dd58-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="4dd58-108">Имя пространства имен, в котором находятся все объявления типов для текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="4dd58-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4dd58-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4dd58-109">Remarks</span></span>  
 <span data-ttu-id="4dd58-110">При использовании исполняемого файла Visual Studio (Devenv.exe) для компиляции проекта, созданного в среде разработки Visual Studio, используйте `/rootnamespace` для указания значения <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>свойство.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="4dd58-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="4dd58-111">В разделе [командной строки devenv](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) подробнее.</span><span class="sxs-lookup"><span data-stu-id="4dd58-111">See [Devenv Command Line Switches](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="4dd58-112">Использование среды CLR дизассемблер MSIL (я`ldasm.exe`) для просмотра имен пространств имен в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="4dd58-112">Use the common language runtime MSIL Disassembler (I`ldasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="4dd58-113">Чтобы задать дополнительные сведения в Visual Studio интегрированная среда разработки</span><span class="sxs-lookup"><span data-stu-id="4dd58-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4dd58-114">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="4dd58-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4dd58-115">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="4dd58-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="4dd58-116">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="4dd58-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="4dd58-117">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="4dd58-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="4dd58-118">3.  Измените значение в **корневое пространство имен** поле.</span><span class="sxs-lookup"><span data-stu-id="4dd58-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4dd58-119">Пример</span><span class="sxs-lookup"><span data-stu-id="4dd58-119">Example</span></span>  
 <span data-ttu-id="4dd58-120">Следующий код компилирует `In.vb` и помещает все объявления типов в пространстве имен `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="4dd58-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4dd58-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4dd58-121">See Also</span></span>  
 <span data-ttu-id="4dd58-122">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="4dd58-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="4dd58-123"> [Ildasm.exe (дизассемблер IL)](https://msdn.microsoft.com/library/f7dy01k1) </span><span class="sxs-lookup"><span data-stu-id="4dd58-123"> [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) </span></span>  
<span data-ttu-id="4dd58-124"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="4dd58-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
