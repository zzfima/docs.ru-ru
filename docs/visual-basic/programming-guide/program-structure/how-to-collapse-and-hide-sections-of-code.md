---
title: Практическое руководство. Сворачивание и сокрытие частей кода
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347411"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="8af7a-102">Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8af7a-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="8af7a-103">Директива `#Region` позволяет сворачивать и скрывать разделы кода в файлах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8af7a-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="8af7a-104">Директива `#Region` позволяет указать блок кода, который можно развернуть или свернуть при использовании редактора кода Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8af7a-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="8af7a-105">Возможность скрывать код выборочно делает файлы более управляемыми и удобочитаемыми.</span><span class="sxs-lookup"><span data-stu-id="8af7a-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="8af7a-106">Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="8af7a-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="8af7a-107">директивы `#Region` поддерживают семантику блока кода, например `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="8af7a-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="8af7a-108">Это означает, что они не могут начинаться в одном блоке и заканчиваться другим; Начало и конец должны находиться в одном блоке.</span><span class="sxs-lookup"><span data-stu-id="8af7a-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="8af7a-109">директивы `#Region` не поддерживаются в функциях.</span><span class="sxs-lookup"><span data-stu-id="8af7a-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="8af7a-110">Сворачивание и скрытие раздела кода</span><span class="sxs-lookup"><span data-stu-id="8af7a-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="8af7a-111">Разместите раздел кода между инструкциями `#Region` и `#End Region`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8af7a-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="8af7a-112">Блок `#Region` можно использовать несколько раз в файле кода. Таким же пользователь может определить собственные блоки процедур и классов, которые, в свою очередь, можно свернуть.</span><span class="sxs-lookup"><span data-stu-id="8af7a-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="8af7a-113">блоки `#Region` также могут быть вложены в другие блоки `#Region`.</span><span class="sxs-lookup"><span data-stu-id="8af7a-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="8af7a-114">Скрытие кода не мешает его компиляции и не влияет на `#If...#End If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8af7a-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="8af7a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8af7a-115">See also</span></span>

- [<span data-ttu-id="8af7a-116">Условная компиляция</span><span class="sxs-lookup"><span data-stu-id="8af7a-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="8af7a-117">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="8af7a-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="8af7a-118">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="8af7a-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="8af7a-119">Структура</span><span class="sxs-lookup"><span data-stu-id="8af7a-119">Outlining</span></span>](/visualstudio/ide/outlining)
