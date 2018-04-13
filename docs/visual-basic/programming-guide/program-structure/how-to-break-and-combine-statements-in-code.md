---
title: Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf6b3ce7e5f9549ca04c4980bd3c91513b343ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="9c635-102">Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c635-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="9c635-103">При написании кода, в некоторых случаях может создать длинный оператор, требующий горизонтальной прокрутки в окне редактора кода.</span><span class="sxs-lookup"><span data-stu-id="9c635-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="9c635-104">Несмотря на то, что это не влияет на внешний код выполняется, он создает сложности при или кто-то еще чтение кода, как он отображается на мониторе.</span><span class="sxs-lookup"><span data-stu-id="9c635-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="9c635-105">В таких случаях следует разбивает один длинный оператор на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="9c635-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="9c635-106">Чтобы разбить один оператор на несколько строк</span><span class="sxs-lookup"><span data-stu-id="9c635-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="9c635-107">Использовать символ продолжения строки — символ подчеркивания (`_`), в точке, в которой необходимо разбиения строки.</span><span class="sxs-lookup"><span data-stu-id="9c635-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="9c635-108">Непосредственно перед знаком подчеркивания должен стоять пробел, а сразу за ним должен быть признак конца строки (возврат каретки).</span><span class="sxs-lookup"><span data-stu-id="9c635-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c635-109">В некоторых случаях если не указан знак продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="9c635-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="9c635-110">Список элементов синтаксиса, для которых можно опустить знак продолжения строки см. в разделе «Неявное продолжение строки» в [инструкции](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="9c635-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="9c635-111">В следующем примере оператор разбивается на четыре строки завершается, все символы продолжения строки, но последней строки.</span><span class="sxs-lookup"><span data-stu-id="9c635-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     <span data-ttu-id="9c635-112">Использование этой последовательности делает код более удобным для чтения, так и при печати.</span><span class="sxs-lookup"><span data-stu-id="9c635-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="9c635-113">Знак продолжения строки должен быть последним символом в строке.</span><span class="sxs-lookup"><span data-stu-id="9c635-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="9c635-114">Вы не выполните с других символов в той же строке.</span><span class="sxs-lookup"><span data-stu-id="9c635-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="9c635-115">Существуют некоторые ограничения на где можно использовать символ продолжения строки; например его нельзя использовать в середине имени аргумента.</span><span class="sxs-lookup"><span data-stu-id="9c635-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="9c635-116">Может быть разбит на список аргументов с символом продолжения строки, но отдельные имена аргументов должны оставаться без изменений.</span><span class="sxs-lookup"><span data-stu-id="9c635-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="9c635-117">Не удается продолжить комментарий с помощью символ продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="9c635-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="9c635-118">Компилятор не изучите символов в комментарии для особое значение.</span><span class="sxs-lookup"><span data-stu-id="9c635-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="9c635-119">Для многострочных комментариев, символа начала комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="9c635-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="9c635-120">Несмотря на то, что размещать каждый оператор в отдельной строке является рекомендуемым методом [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] также позволяет объединять несколько операторов в той же строке.</span><span class="sxs-lookup"><span data-stu-id="9c635-120">Although placing each statement on a separate line is the recommended method, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="9c635-121">Чтобы разместить несколько операторов в одной строке</span><span class="sxs-lookup"><span data-stu-id="9c635-121">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="9c635-122">Операторы разделяются точкой с запятой (`:`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9c635-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9c635-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9c635-123">See Also</span></span>  
 [<span data-ttu-id="9c635-124">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="9c635-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="9c635-125">Операторы</span><span class="sxs-lookup"><span data-stu-id="9c635-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
