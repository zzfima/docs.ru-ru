---
title: Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 680084c39b90d4f664f48559fa21388ce192d999
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955627"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="601df-102">Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="601df-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="601df-103">При написании кода, в некоторых случаях может создать длинный оператор, требующий горизонтальной прокрутки в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="601df-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="601df-104">Несмотря на то, что это не повлияет на способ ваш код, он усложняет задачу вы или кто-то еще чтение кода, как оно отображается на мониторе.</span><span class="sxs-lookup"><span data-stu-id="601df-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="601df-105">В таких случаях следует обдумать разбиение одной инструкции long в несколько строк.</span><span class="sxs-lookup"><span data-stu-id="601df-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="601df-106">Чтобы разбить на несколько строк одной инструкции</span><span class="sxs-lookup"><span data-stu-id="601df-106">To break a single statement into multiple lines</span></span>  
  
- <span data-ttu-id="601df-107">Использовать символ продолжения строки — символ подчеркивания (`_`), в момент, в которое нужно разбиения строки.</span><span class="sxs-lookup"><span data-stu-id="601df-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="601df-108">Непосредственно перед знаком подчеркивания должен стоять пробел, а сразу за ним должен быть признак конца строки (возврат каретки).</span><span class="sxs-lookup"><span data-stu-id="601df-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="601df-109">В некоторых случаях если не указан символ продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="601df-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="601df-110">Список элементов синтаксиса, для которых можно опустить символ продолжения строки, см. в разделе «Неявное продолжение строки» в [инструкций](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="601df-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="601df-111">В следующем примере инструкция разбивается на четыре строки завершает символы продолжения строки, но последняя строка.</span><span class="sxs-lookup"><span data-stu-id="601df-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     <span data-ttu-id="601df-112">С помощью этой последовательности делает код более удобным для чтения, так и печати.</span><span class="sxs-lookup"><span data-stu-id="601df-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="601df-113">Символ продолжения строки должен быть последним символом в строке.</span><span class="sxs-lookup"><span data-stu-id="601df-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="601df-114">Он не может следовать с другими компонентами в той же строке.</span><span class="sxs-lookup"><span data-stu-id="601df-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="601df-115">Существуют ограничения на где можно использовать символ продолжения строки; например его нельзя использовать середине имя аргумента.</span><span class="sxs-lookup"><span data-stu-id="601df-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="601df-116">Вы можете прервать список аргументов с символом продолжения строки, но имена отдельных аргументов должны оставаться без изменений.</span><span class="sxs-lookup"><span data-stu-id="601df-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="601df-117">Не удается продолжить комментарий с помощью символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="601df-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="601df-118">Компилятор не изучите символы в комментарии для специального значения.</span><span class="sxs-lookup"><span data-stu-id="601df-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="601df-119">Для многострочных комментариев, повторите символ комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="601df-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="601df-120">Несмотря на то, что рекомендуется размещать каждый оператор в отдельной строке, Visual Basic также позволяет объединять несколько операторов в той же строке.</span><span class="sxs-lookup"><span data-stu-id="601df-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="601df-121">Чтобы разместить несколько операторов в одной строке</span><span class="sxs-lookup"><span data-stu-id="601df-121">To place multiple statements on the same line</span></span>  
  
- <span data-ttu-id="601df-122">Разместите операторов с запятой (`:`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="601df-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="601df-123">См. также</span><span class="sxs-lookup"><span data-stu-id="601df-123">See also</span></span>

- [<span data-ttu-id="601df-124">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="601df-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="601df-125">Операторы</span><span class="sxs-lookup"><span data-stu-id="601df-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
