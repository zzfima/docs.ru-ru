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
ms.openlocfilehash: c016722332dafa3d3be91a1e9e98cc0ce9a49717
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61908000"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="9dd4d-102">Вложенные структуры управления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dd4d-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="9dd4d-103">Можно разместить операторы управления внутри других операторов управления, например `If...Then...Else` блок `For...Next` цикла.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="9dd4d-104">Операторы управления внутрь другого оператора управления называется *вложенных*.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="9dd4d-105">Число уровней вложения</span><span class="sxs-lookup"><span data-stu-id="9dd4d-105">Nesting Levels</span></span>  
 <span data-ttu-id="9dd4d-106">Структуры элементов управления в Visual Basic могут быть вложенными на всех уровнях.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="9dd4d-107">Это распространенная практика, чтобы повысить удобочитаемость вложенные структуры, добавляйте перед его текст каждого из них.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="9dd4d-108">Редактор Интегрированной среды разработки делает это автоматически.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="9dd4d-109">В следующем примере процедура `sumRows` складывает положительные элементы каждой строки матрицы.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```vb
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
  
 <span data-ttu-id="9dd4d-110">В предыдущем примере первый `Next` инструкции закрывает внутренний `For` цикла, а последний `Next` инструкции закрывает внешний `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="9dd4d-111">Аналогичным образом, во вложенных `If` инструкций, `End If` инструкций автоматически применять к ближайшей предварительного `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="9dd4d-112">Вложенные `Do` циклы работать таким же образом, с самого внутреннего `Loop` оператор соответствует самым внутренним `Do` инструкции.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9dd4d-113">Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="9dd4d-114">Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="9dd4d-115">Чтобы перейти к следующему или предыдущему выделенный ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="9dd4d-116">Вложение структур управления различных типов</span><span class="sxs-lookup"><span data-stu-id="9dd4d-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="9dd4d-117">Можно вложить один тип структуры управления в другой тип.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="9dd4d-118">В следующем примере используется `With` блок `For Each` цикл и вложенные `If` блокирует внутри `With` блока.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```vb
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="9dd4d-119">Перекрывающиеся структуры управления</span><span class="sxs-lookup"><span data-stu-id="9dd4d-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="9dd4d-120">Управляющие структуры не могут перекрываться.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-120">You cannot overlap control structures.</span></span> <span data-ttu-id="9dd4d-121">Это означает, что любой вложенной структуры должны полностью содержаться в следующей внутренней структуры.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="9dd4d-122">Например, следующее расположение является недопустимым из-за `For` цикл завершается раньше внутреннего `With` блока.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Схема, показывающая пример недопустимого вложения.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="9dd4d-124">Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="9dd4d-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd4d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9dd4d-125">See also</span></span>

- [<span data-ttu-id="9dd4d-126">Поток управления</span><span class="sxs-lookup"><span data-stu-id="9dd4d-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="9dd4d-127">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="9dd4d-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="9dd4d-128">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="9dd4d-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="9dd4d-129">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="9dd4d-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
