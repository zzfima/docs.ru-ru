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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4afc0afc2ad63d03f2c4251640d3682b2b184504
ms.lasthandoff: 03/13/2017

---
# <a name="nested-control-structures-visual-basic"></a>Вложенные структуры управления (Visual Basic)
Можно разместить операторы управления внутри других операторов управления, например `If...Then...Else` блок `For...Next` цикла. Операторы управления помещен внутрь другого оператора управления называется *вложенных*.  
  
## <a name="nesting-levels"></a>Число уровней вложения  
 Структуры элементов управления в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] могут быть вложены на всех уровнях. Это часто становится более удобочитаемой вложенные структуры с помощью соответствующих отступов текст каждого из них. Редактор Интегрированная среда разработки автоматически выполняет это действие.  
  
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
  
 В предыдущем примере первый `Next` инструкции закрывает внутренний `For` цикла, а последний `Next` инструкции закрывает внешний `For` цикла.  
  
 Аналогичным образом, во вложенных `If` инструкций, `End If` с ближайшим перед ними автоматически применяются инструкции `If` инструкции. Вложенные `Do` циклы работают таким же образом, с самого внутреннего `Loop` инструкции соответствует самому внутреннему `Do` инструкции.  
  
> [!NOTE]
>  Для многих структур управления что при щелчке ключевого слова, все ключевые слова в структуре выделяются. Например, при нажатии кнопки `If` в `If...Then...Else` конструкции, все экземпляры `If`, `Then`, `ElseIf`, `Else`, и `End If` при построении выделяются. Чтобы переместить выделенные следующего или предыдущего ключевое слово, нажмите клавиши CTRL + SHIFT + СТРЕЛКА ВНИЗ или CTRL + SHIFT + Стрелка вверх.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Вложение различных типов структур управления  
 Можно вложить один тип структуры управления внутрь другого типа. В следующем примере используется `With` внутри блока `For Each` цикл и вложенные `If` блокирует внутри `With` блок.  
  
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
 Управляющие структуры не могут перекрываться. Это означает, что любая вложенная структура должна полностью содержаться внутри следующей внутренней структуры. Например, следующее расположение является недопустимым из-за `For` цикл завершается раньше внутреннего `With` блока.  
  
 ![Схема графика недопустимого вложения](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
Недопустимое вложение структур For и With  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке при компиляции.  
  
## <a name="see-also"></a>См. также  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Структуры критериев](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
