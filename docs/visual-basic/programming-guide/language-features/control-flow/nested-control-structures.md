---
title: Вложенные структуры управления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: ec3d4d477290480cdfa0f5b1c88aa82c81040d11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648076"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="a5b44-102">Вложенные структуры управления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5b44-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="a5b44-103">Можно разместить операторы управления внутри других операторов управления, например `If...Then...Else` блок `For...Next` цикла.</span><span class="sxs-lookup"><span data-stu-id="a5b44-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="a5b44-104">Операторы управления, расположенных внутри другого оператора управления считается *вложенных*.</span><span class="sxs-lookup"><span data-stu-id="a5b44-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="a5b44-105">Число уровней вложения</span><span class="sxs-lookup"><span data-stu-id="a5b44-105">Nesting Levels</span></span>  
 <span data-ttu-id="a5b44-106">Управляющие структуры в Visual Basic могут быть вложенными на всех уровнях.</span><span class="sxs-lookup"><span data-stu-id="a5b44-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="a5b44-107">Это часто можно повысить читаемость вложенные структуры с помощью соответствующих отступов текст каждого из них.</span><span class="sxs-lookup"><span data-stu-id="a5b44-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="a5b44-108">Редактор Интегрированная среда разработки автоматически делает это.</span><span class="sxs-lookup"><span data-stu-id="a5b44-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="a5b44-109">В следующем примере процедура `sumRows` складывает положительные элементы каждой строки матрицы.</span><span class="sxs-lookup"><span data-stu-id="a5b44-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```  
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 <span data-ttu-id="a5b44-110">В предыдущем примере первый `Next` инструкции закрывает внутренний `For` цикл обработки и последнего `Next` инструкции закрывает внешний `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="a5b44-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="a5b44-111">Аналогичным образом, во вложенных `If` инструкций, `End If` выражения автоматически применяются к ближайшим перед ними `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a5b44-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="a5b44-112">Вложенные `Do` циклы работает таким же образом, с самого внутреннего `Loop` оператор соответствует внутренний `Do` инструкции.</span><span class="sxs-lookup"><span data-stu-id="a5b44-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5b44-113">Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются.</span><span class="sxs-lookup"><span data-stu-id="a5b44-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="a5b44-114">Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении.</span><span class="sxs-lookup"><span data-stu-id="a5b44-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="a5b44-115">Чтобы переместить выделенный следующей или предыдущей ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="a5b44-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="a5b44-116">Вложение структур управления различных типов</span><span class="sxs-lookup"><span data-stu-id="a5b44-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="a5b44-117">Можно вложить один тип структуры управления внутрь другого типа.</span><span class="sxs-lookup"><span data-stu-id="a5b44-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="a5b44-118">В следующем примере используется `With` блок `For Each` цикл и вложенными `If` блокирует внутри `With` блока.</span><span class="sxs-lookup"><span data-stu-id="a5b44-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```  
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="a5b44-119">Перекрывающиеся структуры управления</span><span class="sxs-lookup"><span data-stu-id="a5b44-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="a5b44-120">Управляющие структуры не могут перекрываться.</span><span class="sxs-lookup"><span data-stu-id="a5b44-120">You cannot overlap control structures.</span></span> <span data-ttu-id="a5b44-121">Это означает, что любая вложенная структура должен полностью содержаться внутри следующей внутренней структуры.</span><span class="sxs-lookup"><span data-stu-id="a5b44-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="a5b44-122">Например, следующее расположение является недопустимым из-за `For` цикл завершается раньше внутреннего `With` блока.</span><span class="sxs-lookup"><span data-stu-id="a5b44-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="a5b44-123">![Схема графика недопустимого вложения](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="a5b44-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="a5b44-124">Недопустимое вложение структур For и With</span><span class="sxs-lookup"><span data-stu-id="a5b44-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="a5b44-125">Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="a5b44-125">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b44-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a5b44-126">See Also</span></span>  
 [<span data-ttu-id="a5b44-127">Поток управления</span><span class="sxs-lookup"><span data-stu-id="a5b44-127">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="a5b44-128">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="a5b44-128">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="a5b44-129">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="a5b44-129">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="a5b44-130">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="a5b44-130">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
