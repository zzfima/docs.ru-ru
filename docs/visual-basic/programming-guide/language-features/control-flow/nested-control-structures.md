---
title: "Вложенные структуры управления (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "условные операторы, вложенные"
  - "поток управления, вложенные управляющие операторы"
  - "управляющие структуры, вложенные"
  - "вложенные управляющие операторы"
  - "операторы [Visual Basic], поток управления"
  - "структуры, элемент управления вложенного приложения"
  - "код Visual Basic, поток управления"
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Вложенные структуры управления (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Можно разместить операторы управления внутри других операторов управления, например блок `If...Then...Else` в цикле `For...Next`.  Операторы управления, размешенные внутри другого оператора управления, называются *вложенными*.  
  
## Уровень вложенности  
 Структуры элементов управления в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] могут иметь столько уровней вложенности, сколько требуется.  В тексте сообщения для удобства чтения принято выделять вложенные структуры различными отступами для каждого из них.  Редактор среды разработки \(IDE\) автоматически делает это.  
  
 В следующем примере процедура `sumRows` складывает положительные элементы каждой строки матрицы:  
  
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
  
 В предыдущем примере первая инструкция `Next` закрывает внутренний цикл `For`, а последняя инструкция `Next` закрывает внешний цикл `For`.  
  
 Аналогично, если используются вложенные операторы `If`, то операторы `End If` автоматически сопоставляются с ближайшим перед ними оператором `If`.  Вложенные циклы `Do` работают аналогичным образом: самый внутренний оператор `Loop` соответствует самому внутреннему оператору `Do`.  
  
> [!NOTE]
>  Для многих структур управления действует правило, что при нажатии мышью на ключевое слово все ключевые слова в структуре выделяются.  Например, при щелчке `If` в конструкции `If...Then...Else` выделяются все экземпляры `If`, `Then`, `ElseIf`, `Else` и `End If`.  Для перемещения к следующему или предыдущему выделенному ключевому слову нажмите сочетание клавиш CTRL\+SHIFT\+СТРЕЛКА ВНИЗ или CTRL\+SHIFT\+СТРЕЛКА ВВЕРХ.  
  
## Вложение различных типов структур управления  
 Можно вложить один тип структуры управления внутрь другого.  В следующем примере используется блок `With` внутри цикла `For Each` и вложенные блоки `If` внутри блока `With`.  
  
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
  
## Перекрывающиеся структуры управления  
 Нельзя допускать перекрытия структур управления.  Это означает, что любая вложенная структура должна полностью содержаться внутри следующей внутренней структуры.  Например, следующее расположение является недопустимым, так как цикл `For` завершается раньше внутреннего блока `With`.  
  
 ![Схема графика недопустимого вложения](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.png "NestExampleInvalid")  
Недопустимое вложение структур For и With  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор обнаруживает такие перекрывающиеся структуры управления и сигнализирует об ошибке при компиляции.  
  
## См. также  
 [Управление ходом выполнения](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)