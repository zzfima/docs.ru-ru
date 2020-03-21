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
# <a name="nested-control-structures-visual-basic"></a>Вложенные структуры управления (Visual Basic)
Можно разместить контрольные операторы внутри других `If...Then...Else` контрольных `For...Next` инструкций, например блок в цикле. Контрольная выписка, помещенная внутри другого контрольного оператора, как утверждается, *вложена.*  
  
## <a name="nesting-levels"></a>Уровни вложений  
 Структуры управления в Visual Basic могут быть вложены в столько уровней, сколько вы хотите. Это обычная практика, чтобы сделать вложенные структуры более читаемыми путем отступов тела каждого из них. Редактор интегрированной среды разработки (IDE) автоматически делает это.  
  
 В следующем примере `sumRows` процедура объединяет положительные элементы каждой строки матрицы.  
  
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
  
 В предыдущем примере `Next` первое утверждение `For` закрывает внутреннюю `Next` петлю, `For` а последнее — внешнюю.  
  
 Аналогичным образом, в `If` вложенных `End If` операторах операторы `If` автоматически применяются к ближайшему предыдущему заявлению. Вложенные `Do` петли работают аналогичным образом, `Loop` с внутренним утверждением, соответствующим внутреннему `Do` заявлению.  
  
> [!NOTE]
> Для многих структур управления при нажатии на ключевое слово выделены все ключевые слова в структуре. Например, при `If` нажатии `If...Then...Else` на конструкцию `If`выделены `Else`все `End If` экземпляры , `Then` `ElseIf`и в конструкции. Чтобы перейти к следующему или предыдущему выделенному ключевому слову, нажмите CTRL-SHIFT-DOWN ARROW или CTRL-SHIFT-UP ARROW.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Гнездо различных видов структуры управления  
 Вы можете вложить один вид структуры управления в другом виде. В следующем `With` примере используется `For Each` блок внутри `If` петли `With` и вложенные блоки внутри блока.  
  
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
  
## <a name="overlapping-control-structures"></a>Перекрывающиеся структуры управления  
 Вы не можете перекрывать структуры управления. Это означает, что любая вложенная структура должна полностью содержаться в следующей внутренней структуре. Например, следующее расположение является `For` недействительным, поскольку `With` цикл завершается до завершения внутреннего блока.  
  
 ![Диаграмма, отображающая пример недействительного вложенства.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке времени компиляции.  
  
## <a name="see-also"></a>См. также раздел

- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
