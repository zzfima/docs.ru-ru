---
title: "Практическое руководство: разбиение и объединение инструкций в коде (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
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
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ca281035a0bd81a9b52cdd60f2bc59724852709
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="5e64b-102">Практическое руководство. Разбиение и объединение инструкций в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e64b-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="5e64b-103">Во время написания кода может быть создан длинный оператор, требующий горизонтальной прокрутки в окне редактора кода.</span><span class="sxs-lookup"><span data-stu-id="5e64b-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="5e64b-104">Несмотря на то, что это не влияет на способ выполняется код, он создает сложности вы или кто-то еще чтение кода, как он отображается на экране монитора.</span><span class="sxs-lookup"><span data-stu-id="5e64b-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="5e64b-105">В таких случаях следует обдумать разбиение один длинный оператор на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="5e64b-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="5e64b-106">Чтобы разбить один оператор на несколько строк</span><span class="sxs-lookup"><span data-stu-id="5e64b-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="5e64b-107">Использовать знак продолжения строки — символ подчеркивания (`_`), в том месте, в котором разбиения строки.</span><span class="sxs-lookup"><span data-stu-id="5e64b-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="5e64b-108">Непосредственно перед знаком подчеркивания должен стоять пробел, а сразу за ним должен быть признак конца строки (возврат каретки).</span><span class="sxs-lookup"><span data-stu-id="5e64b-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e64b-109">В некоторых случаях если опустить знак продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="5e64b-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="5e64b-110">Список элементов синтаксиса, для которых можно опустить знак продолжения строки, в разделе «Неявное продолжение строки» в [инструкции](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="5e64b-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="5e64b-111">В следующем примере оператор разбивается на четыре строки завершает все символы продолжения строки, но последняя строка.</span><span class="sxs-lookup"><span data-stu-id="5e64b-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     <span data-ttu-id="5e64b-112">[!code-vb[VbVbcnConventions&20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5e64b-112">[!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span></span>  
  
     <span data-ttu-id="5e64b-113">Использование этой последовательности делает код более удобными для чтения, так и при печати.</span><span class="sxs-lookup"><span data-stu-id="5e64b-113">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="5e64b-114">Знак продолжения строки должен быть последним символом в строке.</span><span class="sxs-lookup"><span data-stu-id="5e64b-114">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="5e64b-115">Вы не может следовать с другими объектами в той же строке.</span><span class="sxs-lookup"><span data-stu-id="5e64b-115">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="5e64b-116">Существуют некоторые ограничения, о том, где можно использовать символ продолжения строки; например его нельзя использовать в середине имени аргумента.</span><span class="sxs-lookup"><span data-stu-id="5e64b-116">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="5e64b-117">Можно разбить список аргументов знак продолжения строки, но имена отдельных аргументов должны оставаться неизменными.</span><span class="sxs-lookup"><span data-stu-id="5e64b-117">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="5e64b-118">Не удается продолжить комментарий с помощью символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="5e64b-118">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="5e64b-119">Компилятор не Проверьте символы комментария для особое значение.</span><span class="sxs-lookup"><span data-stu-id="5e64b-119">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="5e64b-120">Для многострочных комментариев, символа начала комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="5e64b-120">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="5e64b-121">Несмотря на то, что размещать каждый оператор в отдельной строке является рекомендуемым методом [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] также позволяет объединять несколько операторов в одной строке.</span><span class="sxs-lookup"><span data-stu-id="5e64b-121">Although placing each statement on a separate line is the recommended method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="5e64b-122">Чтобы разместить несколько операторов в одной строке</span><span class="sxs-lookup"><span data-stu-id="5e64b-122">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="5e64b-123">Операторы разделяются точкой с запятой (`:`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5e64b-123">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     <span data-ttu-id="5e64b-124">[!code-vb[VbVbcnConventions&#10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5e64b-124">[!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e64b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5e64b-125">See Also</span></span>  
 <span data-ttu-id="5e64b-126">[Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="5e64b-126">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="5e64b-127"> [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="5e64b-127"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>
