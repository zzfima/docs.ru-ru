---
title: Вложенные структуры управления (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f2c91bcdd741ef75417fe50b0c08bd0f9bd5ff80
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="nested-control-structures-visual-basic"></a>Вложенные структуры управления (Visual Basic)
Можно разместить операторы управления внутри других операторов управления, например `If...Then...Else` блок `For...Next` цикла. Операторы управления, расположенных внутри другого оператора управления считается *вложенных*.  
  
## <a name="nesting-levels"></a>Число уровней вложения  
 Управляющие структуры в Visual Basic могут быть вложенными на всех уровнях. Это часто можно повысить читаемость вложенные структуры с помощью соответствующих отступов текст каждого из них. Редактор Интегрированная среда разработки автоматически делает это.  
  
 В следующем примере процедура `sumRows` складывает положительные элементы каждой строки матрицы.  
  
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
  
 В предыдущем примере первый `Next` инструкции закрывает внутренний `For` цикл обработки и последнего `Next` инструкции закрывает внешний `For` цикла.  
  
 Аналогичным образом, во вложенных `If` инструкций, `End If` выражения автоматически применяются к ближайшим перед ними `If` инструкции. Вложенные `Do` циклы работает таким же образом, с самого внутреннего `Loop` оператор соответствует внутренний `Do` инструкции.  
  
> [!NOTE]
>  Для многих управляющих структур при щелчке ключевого слова, все ключевые слова в структуре, выделяются. Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` выделяются при построении. Чтобы переместить выделенный следующей или предыдущей ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Вложение структур управления различных типов  
 Можно вложить один тип структуры управления внутрь другого типа. В следующем примере используется `With` блок `For Each` цикл и вложенными `If` блокирует внутри `With` блока.  
  
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
  
## <a name="overlapping-control-structures"></a>Перекрывающиеся структуры управления  
 Управляющие структуры не могут перекрываться. Это означает, что любая вложенная структура должен полностью содержаться внутри следующей внутренней структуры. Например, следующее расположение является недопустимым из-за `For` цикл завершается раньше внутреннего `With` блока.  
  
 ![Схема графика недопустимого вложения](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
Недопустимое вложение структур For и With  
  
 Компилятор Visual Basic обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке времени компиляции.  
  
## <a name="see-also"></a>См. также  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
