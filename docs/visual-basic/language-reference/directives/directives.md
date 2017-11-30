---
title: "Директивы (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8219f17f1b8093b4d02b370c7b008101923b1873
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="directives-visual-basic"></a><span data-ttu-id="7ad91-102">Директивы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ad91-102">Directives (Visual Basic)</span></span>
<span data-ttu-id="7ad91-103">В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7ad91-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ad91-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="7ad91-104">In This Section</span></span>  
 <span data-ttu-id="7ad91-105">[# Директива const](../../../visual-basic/language-reference/directives/const-directive.md) — определение константы компилятора</span><span class="sxs-lookup"><span data-stu-id="7ad91-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="7ad91-106">[Директива #ExternalSource](../../../visual-basic/language-reference/directives/externalsource-directive.md) — задание сопоставления между строками источника и внешнего источника текста</span><span class="sxs-lookup"><span data-stu-id="7ad91-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="7ad91-107">[#If... Then... директивы #Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md) — компиляция выбранных блоков кода</span><span class="sxs-lookup"><span data-stu-id="7ad91-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="7ad91-108">[Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md) — Сворачивание и скрытие частей кода в редакторе Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7ad91-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="7ad91-109">**#Disable, #Enable** — отключение и включение конкретных предупреждений для областей кода.</span><span class="sxs-lookup"><span data-stu-id="7ad91-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="7ad91-110">Можно также отключить и включить список кодов предупреждений с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="7ad91-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7ad91-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7ad91-111">Related Sections</span></span>  
 [<span data-ttu-id="7ad91-112">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ad91-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="7ad91-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ad91-113">Visual Basic</span></span>](../../../visual-basic/index.md)
