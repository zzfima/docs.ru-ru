---
title: "Практическое руководство. Индивидуальное форматирование строк, отображаемых в элементе управления ComboBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "поля со списком, рисование текста"
  - "ComboBox - элемент управления [Windows Forms], рисование пользовательского текста"
  - "ComboBox - элемент управления [Windows Forms], примеры [C#]"
  - "примеры [Windows Forms], ComboBox - элемент управления"
  - "текст, рисование в полях со списками"
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Индивидуальное форматирование строк, отображаемых в элементе управления ComboBox
Этот пример демонстрирует пользовательскую прорисовку текста в элементе управления <xref:System.Windows.Forms.ComboBox>.  Если элемент отвечает определенному условию, он прорисовывается шрифтом большего размер и красным цветом.  
  
## Пример  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Форма Windows Forms.  
  
-   Элемент управления <xref:System.Windows.Forms.ComboBox> с именем `ListBox1` с тремя элементами в свойстве <xref:System.Windows.Forms.ComboBox.Items%2A>.  В этом примере три элемента имеют имя `"One", Two", and Three"`.  Свойство <xref:System.Windows.Forms.ComboBox.DrawMode%2A> `ComboBox1` должно иметь значение <xref:System.Windows.Forms.DrawMode>.  
  
    > [!NOTE]
    >  Этот метод также применяется к элементу управления <xref:System.Windows.Forms.ListBox> – <xref:System.Windows.Forms.ListBox> можно заменить на <xref:System.Windows.Forms.ComboBox>.  
  
-   Ссылки на пространства имен <xref:System.Windows.Forms?displayProperty=fullName> и <xref:System.Drawing?displayProperty=fullName>.  
  
## См. также  
 <xref:System.Windows.Forms.ComboBox.DrawItem>   
 <xref:System.Windows.Forms.DrawItemEventArgs>   
 <xref:System.Windows.Forms.ComboBox.MeasureItem>   
 [Элементы управления Windows Forms со встроенной поддержки рисования владельцем](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)   
 [Элемент управления ListBox](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)   
 [Элемент управления ComboBox](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)