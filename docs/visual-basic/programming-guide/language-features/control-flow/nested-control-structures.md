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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835197"
---
# <a name="nested-control-structures-visual-basic"></a>Вложенные структуры управления (Visual Basic)
Можно разместить операторы управления внутри других операторов управления, например `If...Then...Else` блок `For...Next` цикла. Операторы управления внутрь другого оператора управления называется *вложенных*.  
  
## <a name="nesting-levels"></a>Число уровней вложения  
 Структуры элементов управления в Visual Basic могут быть вложенными на всех уровнях. Это распространенная практика, чтобы повысить удобочитаемость вложенные структуры, добавляйте перед его текст каждого из них. Редактор Интегрированной среды разработки делает это автоматически.  
  
 В следующем примере процедура `sumRows` складывает положительные элементы каждой строки матрицы.  
  
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
  
 В предыдущем примере первый `Next` инструкции закрывает внутренний `For` цикла, а последний `Next` инструкции закрывает внешний `For` цикла.  
  
 Аналогичным образом, во вложенных `If` инструкций, `End If` инструкций автоматически применять к ближайшей предварительного `If` инструкции. Вложенные `Do` циклы работать таким же образом, с самого внутреннего `Loop` оператор соответствует самым внутренним `Do` инструкции.  
  
> [!NOTE]
>  Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются. Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении. Чтобы перейти к следующему или предыдущему выделенный ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Вложение структур управления различных типов  
 Можно вложить один тип структуры управления в другой тип. В следующем примере используется `With` блок `For Each` цикл и вложенные `If` блокирует внутри `With` блока.  
  
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
 Управляющие структуры не могут перекрываться. Это означает, что любой вложенной структуры должны полностью содержаться в следующей внутренней структуры. Например, следующее расположение является недопустимым из-за `For` цикл завершается раньше внутреннего `With` блока.  
  
 ![Схема, показывающая пример недопустимого вложения.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке времени компиляции.  
  
## <a name="see-also"></a>См. также

- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
