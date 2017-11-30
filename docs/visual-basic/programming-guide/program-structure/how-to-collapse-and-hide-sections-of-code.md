---
title: "Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a31f0c8af9b84e87ebe1e5191d72d19be8340f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="f4b8d-102">Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4b8d-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="f4b8d-103">`#Region` Директива позволяет Сворачивание и скрытие частей кода в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] файлов.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files.</span></span> <span data-ttu-id="f4b8d-104">`#Region` Директива позволяет указать блок кода, который можно разворачивать и сворачивать при использовании [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] редактора кода.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] code editor.</span></span> <span data-ttu-id="f4b8d-105">Возможность выборочно скрывать участки кода делает файлы, управляемость и облегчает чтение.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="f4b8d-106">Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="f4b8d-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="f4b8d-107">`#Region`директивы поддерживают семантики блока кода, такие как `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="f4b8d-108">Это означает, не могут начинаться в одном блоке или заканчиваться в другом; Начало и конец должны быть в одном блоке.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="f4b8d-109">`#Region`директивы внутри функции не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="f4b8d-110">Сворачивание и скрытие раздела кода</span><span class="sxs-lookup"><span data-stu-id="f4b8d-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="f4b8d-111">Поместите раздел кода между `#Region` и `#End Region` инструкции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f4b8d-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     <span data-ttu-id="f4b8d-112">`#Region` Блок может использоваться несколько раз в файле кода; таким образом, пользователи могут определять свои собственные блоки процедур и классов, которые в свою очередь, можно свернуть.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="f4b8d-113">`#Region`блоки, также могут быть вложены в другие `#Region` блоков.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f4b8d-114">Скрытие кода не препятствует его компиляции и не влияет на `#If...#End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f4b8d-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b8d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f4b8d-115">See Also</span></span>  
 [<span data-ttu-id="f4b8d-116">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="f4b8d-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="f4b8d-117">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="f4b8d-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="f4b8d-118">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="f4b8d-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="f4b8d-119">Структура</span><span class="sxs-lookup"><span data-stu-id="f4b8d-119">Outlining</span></span>](/visualstudio/ide/outlining)
