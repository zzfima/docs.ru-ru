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
ms.openlocfilehash: f559bf603605873f1b9155e9a96cb367e5420343
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941687"
---
# <a name="nested-control-structures-visual-basic"></a>Вложенные структуры управления (Visual Basic)
Можно разместить управляющие операторы внутри других операторов управления, `If...Then...Else` например блока `For...Next` внутри цикла. Оператор управления, помещенный внутрь другой управляющей инструкции, называется *вложенным*.  
  
## <a name="nesting-levels"></a>Уровни вложенности  
 Структуры управления в Visual Basic могут быть вложены на столько уровней, сколько нужно. Распространенной практикой является более удобочитаемость вложенных структур путем создания отступов для текста каждой из них. Редактор интегрированной среды разработки (IDE) автоматически делает это.  
  
 В следующем примере процедура `sumRows` добавляет вместе положительные элементы каждой строки матрицы.  
  
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
  
 `Next` В предыдущем примере первая инструкция закрывает внутренний `For` цикл, а последняя `Next` инструкция закрывает внешний `For` цикл.  
  
 Аналогично, в `If` вложенных инструкциях `End If` инструкции автоматически применяются к ближайшей `If` предыдущей инструкции. Вложенные `Do` циклы работают аналогичным образом с самой внутренней `Loop` инструкцией, соответствующей `Do` самой внутренней инструкции.  
  
> [!NOTE]
> Для многих структур управления при щелчке ключевого слова все ключевые слова в структуре выделяются. `If` Например, если щелкнуть `If...Then...Else` `Then` `End If` `Else`конструкцию, будут выделены `ElseIf`все экземпляры ,,,ивконструкции.`If` Чтобы перейти к следующему или предыдущему выделенному ключевому слову, нажмите клавиши CTRL + SHIFT + стрелка вниз или CTRL + SHIFT + стрелка вверх.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Вложение различных видов структур управления  
 Один тип структуры управления можно вложить в другой тип. В следующем примере `With` используется блок `For Each` внутри цикла `With` и вложенные `If` блоки внутри блока.  
  
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
  
## <a name="overlapping-control-structures"></a>Перекрывающиеся структуры элементов управления  
 Нельзя перекрывать структуры управления. Это означает, что любая вложенная структура должна полностью содержаться в следующей самой внутренней структуре. Например, следующее расположение недопустимо, так как `For` цикл завершается до завершения внутреннего `With` блока.  
  
 ![Схема, на которой показан пример недопустимого вложения.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры элементов управления и сигнализирует об ошибке во время компиляции.  
  
## <a name="see-also"></a>См. также

- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
