---
title: "Вложенные структуры управления (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, control flow
- control structures, nested
- conditional statements, nested
- statements [Visual Basic], control flow
- control flow, nested control statements
- structures, nested control
- nested control statements
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8275a0628c8593d9e6c55ef27adcde2acec31547
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="bf3ba-102">Вложенные структуры управления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf3ba-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="bf3ba-103">Можно разместить операторы управления внутри других операторов управления, например `If...Then...Else` блок `For...Next` цикла.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="bf3ba-104">Операторы управления помещен внутрь другого оператора управления называется *вложенных*.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="bf3ba-105">Число уровней вложения</span><span class="sxs-lookup"><span data-stu-id="bf3ba-105">Nesting Levels</span></span>  
 <span data-ttu-id="bf3ba-106">Структуры элементов управления в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] могут быть вложены на всех уровнях.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-106">Control structures in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can be nested to as many levels as you want.</span></span> <span data-ttu-id="bf3ba-107">Это часто становится более удобочитаемой вложенные структуры с помощью соответствующих отступов текст каждого из них.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="bf3ba-108">Редактор Интегрированная среда разработки автоматически выполняет это действие.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="bf3ba-109">В следующем примере процедура `sumRows` складывает положительные элементы каждой строки матрицы.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="bf3ba-110">В предыдущем примере первый `Next` инструкции закрывает внутренний `For` цикла, а последний `Next` инструкции закрывает внешний `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="bf3ba-111">Аналогичным образом, во вложенных `If` инструкций, `End If` с ближайшим перед ними автоматически применяются инструкции `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="bf3ba-112">Вложенные `Do` циклы работают таким же образом, с самого внутреннего `Loop` инструкции соответствует самому внутреннему `Do` инструкции.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf3ba-113">Для многих структур управления что при щелчке ключевого слова, все ключевые слова в структуре выделяются.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="bf3ba-114">Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` при построении выделяются.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="bf3ba-115">Чтобы переместить выделенные следующего или предыдущего ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="bf3ba-116">Вложение различных типов структур управления</span><span class="sxs-lookup"><span data-stu-id="bf3ba-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="bf3ba-117">Можно вложить один тип структуры управления внутрь другого типа.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="bf3ba-118">В следующем примере используется `With` внутри блока `For Each` цикл и вложенные `If` блокирует внутри `With` блок.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="bf3ba-119">Перекрывающиеся структуры управления</span><span class="sxs-lookup"><span data-stu-id="bf3ba-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="bf3ba-120">Управляющие структуры не могут перекрываться.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-120">You cannot overlap control structures.</span></span> <span data-ttu-id="bf3ba-121">Это означает, что любая вложенная структура должна полностью содержаться внутри следующей внутренней структуры.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="bf3ba-122">Например, следующее расположение является недопустимым из-за `For` цикл завершается раньше внутреннего `With` блока.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="bf3ba-123">![Схема графика недопустимого вложения](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="bf3ba-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="bf3ba-124">Недопустимое вложение структур For и With</span><span class="sxs-lookup"><span data-stu-id="bf3ba-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="bf3ba-125">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке при компиляции.</span><span class="sxs-lookup"><span data-stu-id="bf3ba-125">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3ba-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bf3ba-126">See Also</span></span>  
 <span data-ttu-id="bf3ba-127">[Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="bf3ba-127">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="bf3ba-128"> [Структуры критериев](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="bf3ba-128"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="bf3ba-129"> [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="bf3ba-129"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="bf3ba-130"> [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="bf3ba-130"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)</span></span>
