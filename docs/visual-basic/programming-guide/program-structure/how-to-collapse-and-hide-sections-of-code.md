---
title: Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: bf2a7188456097ac227039e4d902a14eb182664c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758279"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="38f21-102">Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38f21-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="38f21-103">`#Region` Директива позволяет сворачивать и скрывать разделы кода в файлах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="38f21-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="38f21-104">`#Region` Директива позволяет указать блок кода, который можно разворачивать и сворачивать при использовании в редакторе кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="38f21-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="38f21-105">Возможность выборочно скрыть код делает файлы стала более управляемой и более удобными для чтения.</span><span class="sxs-lookup"><span data-stu-id="38f21-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="38f21-106">Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="38f21-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="38f21-107">`#Region` директивы поддерживают семантики блока кода, такие как `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="38f21-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="38f21-108">Это означает, что они не может начинаться в одном блоке и заканчиваться в другом; Начало и конец должны быть в одном блоке.</span><span class="sxs-lookup"><span data-stu-id="38f21-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="38f21-109">`#Region` директивы не поддерживаются в функциях.</span><span class="sxs-lookup"><span data-stu-id="38f21-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="38f21-110">Чтобы свернуть и скрыть часть кода</span><span class="sxs-lookup"><span data-stu-id="38f21-110">To collapse and hide a section of code</span></span>  
  
- <span data-ttu-id="38f21-111">Поместите раздел кода между `#Region` и `#End Region` инструкции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="38f21-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     <span data-ttu-id="38f21-112">`#Region` Блок может использоваться несколько раз в файле кода; таким образом, пользователи могут определять свои собственные блоки процедур и классов, которые в свою очередь, может быть свернута.</span><span class="sxs-lookup"><span data-stu-id="38f21-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="38f21-113">`#Region` блоки также могут быть вложены в другие `#Region` блоков.</span><span class="sxs-lookup"><span data-stu-id="38f21-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38f21-114">Скрытие кода не препятствует его компиляции и не влияет на `#If...#End If` инструкций.</span><span class="sxs-lookup"><span data-stu-id="38f21-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f21-115">См. также</span><span class="sxs-lookup"><span data-stu-id="38f21-115">See also</span></span>

- [<span data-ttu-id="38f21-116">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="38f21-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="38f21-117">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="38f21-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="38f21-118">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="38f21-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="38f21-119">Структура</span><span class="sxs-lookup"><span data-stu-id="38f21-119">Outlining</span></span>](/visualstudio/ide/outlining)
