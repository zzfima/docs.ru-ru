---
title: Практическое руководство. Вызов процедуры, возвращающей значение
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 7f5d46babf31ea3c6babb29c0f1c08a23e51d598
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340731"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="3c66a-102">Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c66a-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="3c66a-103">`Function` процедура возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="3c66a-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="3c66a-104">Его можно вызвать, указав его имя и аргументы в правой части оператора присваивания или в выражении.</span><span class="sxs-lookup"><span data-stu-id="3c66a-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="3c66a-105">Вызов процедуры Function в выражении</span><span class="sxs-lookup"><span data-stu-id="3c66a-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="3c66a-106">Используйте `Function` имя процедуры так же, как и переменную.</span><span class="sxs-lookup"><span data-stu-id="3c66a-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="3c66a-107">Можно использовать вызов процедуры `Function` в любом месте, где можно использовать переменную или константу в выражении.</span><span class="sxs-lookup"><span data-stu-id="3c66a-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="3c66a-108">Чтобы заключить список аргументов, выполните имя процедуры с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="3c66a-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="3c66a-109">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="3c66a-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="3c66a-110">Однако использование круглых скобок упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="3c66a-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="3c66a-111">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="3c66a-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="3c66a-112">Убедитесь, что аргументы указываются в том же порядке, в котором процедура `Function` определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3c66a-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="3c66a-113">Кроме того, можно передать один или несколько аргументов по имени.</span><span class="sxs-lookup"><span data-stu-id="3c66a-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="3c66a-114">Дополнительные сведения см. в разделе [Передача аргументов по положению и по имени](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="3c66a-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="3c66a-115">Значение, возвращаемое процедурой, участвует в выражении точно так же, как значение переменной или константы.</span><span class="sxs-lookup"><span data-stu-id="3c66a-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="3c66a-116">Вызов процедуры Function в операторе присваивания</span><span class="sxs-lookup"><span data-stu-id="3c66a-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="3c66a-117">Используйте `Function` имя процедуры после знака равенства (`=`) в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="3c66a-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="3c66a-118">Чтобы заключить список аргументов, выполните имя процедуры с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="3c66a-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="3c66a-119">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="3c66a-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="3c66a-120">Однако использование круглых скобок упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="3c66a-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="3c66a-121">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="3c66a-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="3c66a-122">Убедитесь, что аргументы указываются в том же порядке, в котором `Function` процедура определяет соответствующие параметры, если не передать их по имени.</span><span class="sxs-lookup"><span data-stu-id="3c66a-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="3c66a-123">Значение, возвращаемое процедурой, хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="3c66a-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c66a-124">Пример</span><span class="sxs-lookup"><span data-stu-id="3c66a-124">Example</span></span>  
 <span data-ttu-id="3c66a-125">В следующем примере вызывается Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> для получения значения переменной среды операционной системы.</span><span class="sxs-lookup"><span data-stu-id="3c66a-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="3c66a-126">Первая строка вызывает `Environ` в выражении, а вторая строка вызывает его в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="3c66a-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="3c66a-127">`Environ` принимает имя переменной в качестве единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="3c66a-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="3c66a-128">Он возвращает значение переменной в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="3c66a-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="3c66a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3c66a-129">See also</span></span>

- [<span data-ttu-id="3c66a-130">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="3c66a-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="3c66a-131">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="3c66a-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3c66a-132">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="3c66a-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="3c66a-133">Практическое руководство. Создание процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="3c66a-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="3c66a-134">Практическое руководство. Возврат значения из процедуры</span><span class="sxs-lookup"><span data-stu-id="3c66a-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="3c66a-135">Практическое руководство. Вызов процедуры, которая не возвращает значение</span><span class="sxs-lookup"><span data-stu-id="3c66a-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
