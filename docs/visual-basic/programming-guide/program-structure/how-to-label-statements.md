---
title: Практическое руководство. Операторы меток
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: be116ac8046c43e89e44c2d9127c6131e4dfaa52
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347381"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="26599-102">Практическое руководство. Операторы меток (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26599-102">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="26599-103">Блоки инструкций состоят из строк кода, разделенных двоеточиями.</span><span class="sxs-lookup"><span data-stu-id="26599-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="26599-104">Строки кода, которым предшествует идентифицирующая строка или целое число, говорят о *метке*.</span><span class="sxs-lookup"><span data-stu-id="26599-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="26599-105">Метки операторов используются для пометки строки кода, чтобы она определялась для использования с такими инструкциями, как `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="26599-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="26599-106">Метки могут быть либо допустимыми Visual Basic идентификаторами, например, для идентификации программных элементов, либо целочисленными литералами.</span><span class="sxs-lookup"><span data-stu-id="26599-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="26599-107">Метка должна располагаться в начале строки исходного кода, после которой должно следовать двоеточие, независимо от того, за чем следует оператор в той же строке.</span><span class="sxs-lookup"><span data-stu-id="26599-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="26599-108">Компилятор определяет метки, проверяя, соответствует ли начало строки любому уже определенному идентификатору.</span><span class="sxs-lookup"><span data-stu-id="26599-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="26599-109">Если это не так, компилятор предполагает, что это метка.</span><span class="sxs-lookup"><span data-stu-id="26599-109">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="26599-110">Метки имеют собственную область объявления и не мешают другим идентификаторам.</span><span class="sxs-lookup"><span data-stu-id="26599-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="26599-111">Областью действия метки является тело метода.</span><span class="sxs-lookup"><span data-stu-id="26599-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="26599-112">Объявление метки имеет приоритет при любой неоднозначной ситуации.</span><span class="sxs-lookup"><span data-stu-id="26599-112">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="26599-113">Метки могут использоваться только в исполняемых инструкциях внутри методов.</span><span class="sxs-lookup"><span data-stu-id="26599-113">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="26599-114">Добавление метки к строке кода</span><span class="sxs-lookup"><span data-stu-id="26599-114">To label a line of code</span></span>

<span data-ttu-id="26599-115">Поместите идентификатор, за которым следует двоеточие, в начало строки исходного кода.</span><span class="sxs-lookup"><span data-stu-id="26599-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="26599-116">Например, следующие строки кода помечены как `Jump` и `120`соответственно:</span><span class="sxs-lookup"><span data-stu-id="26599-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="26599-117">См. также</span><span class="sxs-lookup"><span data-stu-id="26599-117">See also</span></span>

- [<span data-ttu-id="26599-118">Операторы</span><span class="sxs-lookup"><span data-stu-id="26599-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="26599-119">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="26599-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="26599-120">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="26599-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
