---
title: Вложенные структуры управления
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
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266928"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="ea926-102">Вложенные структуры управления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea926-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="ea926-103">Можно разместить контрольные операторы внутри других `If...Then...Else` контрольных `For...Next` инструкций, например блок в цикле.</span><span class="sxs-lookup"><span data-stu-id="ea926-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="ea926-104">Контрольная выписка, помещенная внутри другого контрольного оператора, как утверждается, *вложена.*</span><span class="sxs-lookup"><span data-stu-id="ea926-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="ea926-105">Уровни вложений</span><span class="sxs-lookup"><span data-stu-id="ea926-105">Nesting Levels</span></span>  
 <span data-ttu-id="ea926-106">Структуры управления в Visual Basic могут быть вложены в столько уровней, сколько вы хотите.</span><span class="sxs-lookup"><span data-stu-id="ea926-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="ea926-107">Это обычная практика, чтобы сделать вложенные структуры более читаемыми путем отступов тела каждого из них.</span><span class="sxs-lookup"><span data-stu-id="ea926-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="ea926-108">Редактор интегрированной среды разработки (IDE) автоматически делает это.</span><span class="sxs-lookup"><span data-stu-id="ea926-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="ea926-109">В следующем примере `sumRows` процедура объединяет положительные элементы каждой строки матрицы.</span><span class="sxs-lookup"><span data-stu-id="ea926-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="ea926-110">В предыдущем примере `Next` первое утверждение `For` закрывает внутреннюю `Next` петлю, `For` а последнее — внешнюю.</span><span class="sxs-lookup"><span data-stu-id="ea926-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="ea926-111">Аналогичным образом, в `If` вложенных `End If` операторах операторы `If` автоматически применяются к ближайшему предыдущему заявлению.</span><span class="sxs-lookup"><span data-stu-id="ea926-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="ea926-112">Вложенные `Do` петли работают аналогичным образом, `Loop` с внутренним утверждением, соответствующим внутреннему `Do` заявлению.</span><span class="sxs-lookup"><span data-stu-id="ea926-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea926-113">Для многих структур управления при нажатии на ключевое слово выделены все ключевые слова в структуре.</span><span class="sxs-lookup"><span data-stu-id="ea926-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="ea926-114">Например, при `If` нажатии `If...Then...Else` на конструкцию `If`выделены `Else`все `End If` экземпляры , `Then` `ElseIf`и в конструкции.</span><span class="sxs-lookup"><span data-stu-id="ea926-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="ea926-115">Чтобы перейти к следующему или предыдущему выделенному ключевому слову, нажмите CTRL-SHIFT-DOWN ARROW или CTRL-SHIFT-UP ARROW.</span><span class="sxs-lookup"><span data-stu-id="ea926-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="ea926-116">Гнездо различных видов структуры управления</span><span class="sxs-lookup"><span data-stu-id="ea926-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="ea926-117">Вы можете вложить один вид структуры управления в другом виде.</span><span class="sxs-lookup"><span data-stu-id="ea926-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="ea926-118">В следующем `With` примере используется `For Each` блок внутри `If` петли `With` и вложенные блоки внутри блока.</span><span class="sxs-lookup"><span data-stu-id="ea926-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="ea926-119">Перекрывающиеся структуры управления</span><span class="sxs-lookup"><span data-stu-id="ea926-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="ea926-120">Вы не можете перекрывать структуры управления.</span><span class="sxs-lookup"><span data-stu-id="ea926-120">You cannot overlap control structures.</span></span> <span data-ttu-id="ea926-121">Это означает, что любая вложенная структура должна полностью содержаться в следующей внутренней структуре.</span><span class="sxs-lookup"><span data-stu-id="ea926-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="ea926-122">Например, следующее расположение является `For` недействительным, поскольку `With` цикл завершается до завершения внутреннего блока.</span><span class="sxs-lookup"><span data-stu-id="ea926-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Диаграмма, отображающая пример недействительного вложенства.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="ea926-124">Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="ea926-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea926-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ea926-125">See also</span></span>

- [<span data-ttu-id="ea926-126">Поток управления</span><span class="sxs-lookup"><span data-stu-id="ea926-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="ea926-127">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="ea926-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="ea926-128">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="ea926-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="ea926-129">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="ea926-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
