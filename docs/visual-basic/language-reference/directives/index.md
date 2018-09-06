---
title: Директивы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43736611"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="96c1b-102">Директивы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96c1b-102">Directives (Visual Basic)</span></span>
<span data-ttu-id="96c1b-103">В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96c1b-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96c1b-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="96c1b-104">In This Section</span></span>  
 <span data-ttu-id="96c1b-105">[#Const-директива](../../../visual-basic/language-reference/directives/const-directive.md) — определение константы компилятора</span><span class="sxs-lookup"><span data-stu-id="96c1b-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="96c1b-106">[Директива #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) --сопоставления между строками источника и текста, внешним по отношению к источнику</span><span class="sxs-lookup"><span data-stu-id="96c1b-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="96c1b-107">[#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md) — компиляция выбранных блоков кода</span><span class="sxs-lookup"><span data-stu-id="96c1b-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="96c1b-108">[Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md) — Сворачивание и скрытие частей кода в редакторе Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96c1b-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="96c1b-109">**#Disable, #Enable** — отключение и включение конкретных предупреждений для областей кода.</span><span class="sxs-lookup"><span data-stu-id="96c1b-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="96c1b-110">Можно также отключить и включить список кодов предупреждений с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="96c1b-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="96c1b-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="96c1b-111">Related Sections</span></span>  
 [<span data-ttu-id="96c1b-112">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96c1b-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="96c1b-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96c1b-113">Visual Basic</span></span>](../../../visual-basic/index.md)
