---
title: Практическое руководство. Разбиение и объединение операторов в коде (Visual Basic)
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
ms.openlocfilehash: f17f815ea0f1f91284d3223ff233a87dc7ff71eb
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70892684"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="38939-102">Практическое руководство. Разбиение и объединение операторов в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38939-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="38939-103">При написании кода иногда можно создавать длинные операторы, требующие горизонтальной прокрутки в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="38939-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="38939-104">Хотя это не влияет на способ выполнения кода, он затрудняет чтение кода в том виде, в котором он отображается на мониторе.</span><span class="sxs-lookup"><span data-stu-id="38939-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="38939-105">В таких случаях следует рассмотреть возможность разбиения одного длинного оператора на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="38939-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="38939-106">Разбиение одного оператора на несколько строк</span><span class="sxs-lookup"><span data-stu-id="38939-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="38939-107">Используйте символ продолжения строки, который является подчеркиванием (`_`), в точке, в которой должна прерываться линия.</span><span class="sxs-lookup"><span data-stu-id="38939-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="38939-108">Символу подчеркивания должен предшествовать пробел и сразу за ним следует символ конца строки (возврат каретки) или (начиная с версии 16,0) комментарий, за которым следует символ возврата каретки.</span><span class="sxs-lookup"><span data-stu-id="38939-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return) or (starting with version 16.0) a comment followed by a carriage return.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="38939-109">В некоторых случаях, если опустить символ продолжения строки, компилятор Visual Basic неявно продолжит инструкцию на следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="38939-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="38939-110">Список элементов синтаксиса, для которых можно опустить символ продолжения строки, см. в разделе «неявные продолжения строки» в [инструкциях](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="38939-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="38939-111">В следующем примере инструкция разбивается на четыре строки с символами продолжения строки, завершающими все, кроме последней строки.</span><span class="sxs-lookup"><span data-stu-id="38939-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     <span data-ttu-id="38939-112">Использование этой последовательности упрощает чтение кода в сети и при печати.</span><span class="sxs-lookup"><span data-stu-id="38939-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="38939-113">Символ продолжения строки должен быть последним символом в строке.</span><span class="sxs-lookup"><span data-stu-id="38939-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="38939-114">Вы не можете подписаться на него другим в той же строке.</span><span class="sxs-lookup"><span data-stu-id="38939-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="38939-115">Существуют некоторые ограничения, в которых можно использовать символ продолжения строки. Например, нельзя использовать его в середине имени аргумента.</span><span class="sxs-lookup"><span data-stu-id="38939-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="38939-116">Можно прервать список аргументов с помощью символа продолжения строки, но отдельные имена аргументов должны оставаться неизменными.</span><span class="sxs-lookup"><span data-stu-id="38939-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="38939-117">Комментарий нельзя продолжить с помощью символа продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="38939-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="38939-118">Компилятор не проверяет символы в комментарии на наличие специального значения.</span><span class="sxs-lookup"><span data-stu-id="38939-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="38939-119">Для многострочного комментария повторите символ комментария (`'`) в каждой строке.</span><span class="sxs-lookup"><span data-stu-id="38939-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="38939-120">Хотя размещение каждой инструкции в отдельной строке является рекомендуемым методом, Visual Basic также позволяет размещать несколько инструкций в одной строке.</span><span class="sxs-lookup"><span data-stu-id="38939-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="38939-121">Размещение нескольких инструкций на одной строке</span><span class="sxs-lookup"><span data-stu-id="38939-121">To place multiple statements on the same line</span></span>  
  
- <span data-ttu-id="38939-122">Разделите операторы с помощью двоеточия`:`(), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="38939-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="38939-123">См. также</span><span class="sxs-lookup"><span data-stu-id="38939-123">See also</span></span>

- [<span data-ttu-id="38939-124">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="38939-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="38939-125">Операторы</span><span class="sxs-lookup"><span data-stu-id="38939-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
