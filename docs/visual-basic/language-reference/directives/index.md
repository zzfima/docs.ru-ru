---
title: Директивы
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838147"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="93cdd-102">Директивы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93cdd-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="93cdd-103">В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="93cdd-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93cdd-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="93cdd-104">In This Section</span></span>  

 <span data-ttu-id="93cdd-105">[Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md) — Определение константы компилятора</span><span class="sxs-lookup"><span data-stu-id="93cdd-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="93cdd-106">[Директива #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) — указывает сопоставление между исходными строками и текстом, внешним по отношению к источнику</span><span class="sxs-lookup"><span data-stu-id="93cdd-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="93cdd-107">[#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --компилировать выбранные блоки кода</span><span class="sxs-lookup"><span data-stu-id="93cdd-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="93cdd-108">[Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md) — сворачивание и скрытие разделов кода в редакторе Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93cdd-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="93cdd-109">**#Disable, #Enable** — отключение и включение конкретных предупреждений для регионов кода.</span><span class="sxs-lookup"><span data-stu-id="93cdd-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="93cdd-110">Можно также отключить и включить список кодов предупреждений с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="93cdd-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="93cdd-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="93cdd-111">Related Sections</span></span>  

 [<span data-ttu-id="93cdd-112">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93cdd-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  