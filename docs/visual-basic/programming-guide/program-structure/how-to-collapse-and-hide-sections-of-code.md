---
title: "Практическое руководство: сворачивание и скрытие частей кода (Visual Basic) | Документы Microsoft"
ms.custom: 
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
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
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
ms.openlocfilehash: 4dcd5cd5d79629fd008534112cb72d5bcfec476e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="85181-102">Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85181-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="85181-103">`#Region` Директива позволяет Сворачивание и скрытие частей кода в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлов.</span><span class="sxs-lookup"><span data-stu-id="85181-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files.</span></span> <span data-ttu-id="85181-104">`#Region` Директива позволяет указать блок кода, который можно разворачивать и сворачивать при использовании [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] редактора кода.</span><span class="sxs-lookup"><span data-stu-id="85181-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] code editor.</span></span> <span data-ttu-id="85181-105">Возможность избирательно прятать код делает файлы более управляемыми и легче читать.</span><span class="sxs-lookup"><span data-stu-id="85181-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="85181-106">Дополнительные сведения см. в разделе [Структура](https://docs.microsoft.com/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="85181-106">For more information, see [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="85181-107">`#Region`директивы поддерживают семантики блока кода, например `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="85181-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="85181-108">Это значит, они не может начинаться в одном блоке и заканчиваться в другом; Начало и конец должны быть в одном блоке.</span><span class="sxs-lookup"><span data-stu-id="85181-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="85181-109">`#Region`директивы не поддерживаются внутри функций.</span><span class="sxs-lookup"><span data-stu-id="85181-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="85181-110">Чтобы свернуть и спрятать раздел кода</span><span class="sxs-lookup"><span data-stu-id="85181-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="85181-111">Поместите раздел кода между `#Region` и `#End Region` операторы, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="85181-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     <span data-ttu-id="85181-112">[!code-vb[VbVbalrConditionalComp №&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="85181-112">[!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span></span>  
  
     <span data-ttu-id="85181-113">`#Region` Блок может использоваться несколько раз в файле кода; таким образом, пользователи могут определять свои собственные блоки процедур и классов, которые в свою очередь, можно свернуть.</span><span class="sxs-lookup"><span data-stu-id="85181-113">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="85181-114">`#Region`блоки также могут быть вложены в другие `#Region` блоков.</span><span class="sxs-lookup"><span data-stu-id="85181-114">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85181-115">Скрытие кода не препятствует его компиляции и не влияет на `#If...#End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="85181-115">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85181-116">См. также</span><span class="sxs-lookup"><span data-stu-id="85181-116">See Also</span></span>  
 <span data-ttu-id="85181-117">[Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="85181-117">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<span data-ttu-id="85181-118"> [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="85181-118"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="85181-119"> [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="85181-119"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="85181-120"> [Структура](https://docs.microsoft.com/visualstudio/ide/outlining)</span><span class="sxs-lookup"><span data-stu-id="85181-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining)</span></span>
