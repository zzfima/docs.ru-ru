---
title: Практическое руководство. Операторы меток (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: df368bdba73ca35dd70bdd2f4e88cc10af894b5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="ffa60-102">Практическое руководство. Операторы меток (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffa60-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="ffa60-103">Блоки операторов состоят из строк кода, разделенных точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="ffa60-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="ffa60-104">Строки кода, предшествует идентификатор или целое число, называются *с меткой*.</span><span class="sxs-lookup"><span data-stu-id="ffa60-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="ffa60-105">Метки операторов используются пометить строку кода для обозначения при использовании операторами, такие как `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="ffa60-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="ffa60-106">Метки могут быть либо допустимые идентификаторы Visual Basic, например те, которые идентифицируют элементы программы, либо целочисленные константы.</span><span class="sxs-lookup"><span data-stu-id="ffa60-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="ffa60-107">Метки должны находиться в начале строки исходного кода и должен быть с двоеточием, независимо от того за ним следует с помощью инструкции в той же строке.</span><span class="sxs-lookup"><span data-stu-id="ffa60-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="ffa60-108">Компилятор распознает метки, проверяя, совпадает ли начало строки любой идентификатор уже определен.</span><span class="sxs-lookup"><span data-stu-id="ffa60-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="ffa60-109">Если этого не произошло, компилятор предполагает, что это метка.</span><span class="sxs-lookup"><span data-stu-id="ffa60-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="ffa60-110">Метки имеют собственную область объявления и не пересекаются с другими идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="ffa60-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="ffa60-111">Областью метки является тело метода.</span><span class="sxs-lookup"><span data-stu-id="ffa60-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="ffa60-112">Объявление метки приоритет двоеточиями.</span><span class="sxs-lookup"><span data-stu-id="ffa60-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffa60-113">Метки могут использоваться только для исполняемых инструкций внутри методов.</span><span class="sxs-lookup"><span data-stu-id="ffa60-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="ffa60-114">Пометка строки кода</span><span class="sxs-lookup"><span data-stu-id="ffa60-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="ffa60-115">Поместите идентификатора, за которым следует двоеточие, в начале строки исходного кода.</span><span class="sxs-lookup"><span data-stu-id="ffa60-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="ffa60-116">Например, следующие строки кода помечаются `Jump` и `120`соответственно:</span><span class="sxs-lookup"><span data-stu-id="ffa60-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ffa60-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ffa60-117">See Also</span></span>  
 [<span data-ttu-id="ffa60-118">Операторы</span><span class="sxs-lookup"><span data-stu-id="ffa60-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="ffa60-119">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="ffa60-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="ffa60-120">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="ffa60-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
