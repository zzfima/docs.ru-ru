---
title: "International Fonts in Windows Forms and Controls | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "fonts, international"
  - "international applications [Windows Forms], character display"
  - "fonts, globalization considerations"
  - "localization [Windows Forms], fonts"
  - "Windows Forms controls, labels"
  - "font fallback in Windows Forms"
  - "globalization [Windows Forms], character sets"
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# International Fonts in Windows Forms and Controls
Рекомендуемым способом выбора шрифтов в международных приложениях является как возможно более широкое использование режима подмены шрифта.  Это означает, что система сама определяет, к какому языку относится тот или иной знак.  
  
## Применение подмены шрифта  
 Для того чтобы воспользоваться этой возможностью, не задавайте значение свойства <xref:System.Drawing.Font> для форм или каких\-либо других элементов.  Приложение автоматически задействует системный шрифт по умолчанию, который зависит от языка локализованной операционной системы.  При выполнении приложения система автоматически выбирает правильный шрифт для языка и региональных параметров, установленных в операционной системе.  
  
 Данное правило, в силу которого шрифт не задается, имеет одно исключение, связанное с изменением начертания шрифта.  Это может оказаться важным для приложения, в котором пользователь нажимает кнопку, чтобы текст в текстовом поле был выделен полужирным шрифтом.  Для этого потребуется написать функцию, которая изменяла бы начертание шрифта в текстовом поле на полужирное в зависимости от шрифта формы.  Важно вызвать эту функцию в двух местах: в обработчике события <xref:System.Windows.Forms.Control.Click> кнопки и в обработчике события <xref:System.Windows.Forms.Control.FontChanged>.  Если функция вызывается только в обработчике события <xref:System.Windows.Forms.Control.Click>, то при изменении семейства шрифтов для всей формы каким\-либо другим фрагментом кода шрифт текстового поля не будет изменен вместе с остальной частью формы.  
  
```  
' Visual Basic  
Private Sub MakeBold()  
   ' Change the TextBox to a bold version of the form font  
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
   ' Clicking this button makes the TextBox bold  
   MakeBold()  
End Sub  
  
Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged  
   ' If the TextBox is already bold and the form's font changes,  
   ' change the TextBox to a bold version of the new form font  
   If (TextBox1.Font.Style = FontStyle.Bold) Then  
      MakeBold()  
   End If  
End Sub  
  
// C#  
private void button1_Click(object sender, System.EventArgs e)  
{  
   // Clicking this button makes the TextBox bold  
   MakeBold();  
}  
  
private void MakeBold()   
{  
   // Change the TextBox to a bold version of the form's font  
   textBox1.Font = new Font(this.Font, FontStyle.Bold);  
}  
  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
   // If the TextBox is already bold and the form's font changes,  
   // change the TextBox to a bold version of the new form font  
   if (textBox1.Font.Style == FontStyle.Bold)   
   {  
      MakeBold();  
   }  
}  
```  
  
 Однако при локализации приложения на некоторых языках полужирный шрифт может выглядеть некрасиво.  Если это так, то локализаторам необходима возможность переключать начертание шрифта с обычного на полужирное и обратно.  Поскольку локализаторы, как правило, не являются разработчиками и не имеют доступа к исходному коду, работая только с файлами ресурсов, эту возможность требуется реализовать в файлах ресурсов.  Для этого необходимо установить для свойства <xref:System.Drawing.Font.Bold%2A> значение `true`.  Таким образом, в файлах ресурсов записывается начертание шрифта, и локализаторы могут видоизменять его.  Затем следует написать код, который сбрасывает шрифт на основании того, каким был шрифт формы, но использует начертание шрифта, указанное в файле ресурсов. Этот код следует вставить после метода `InitializeComponent` .  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## См. также  
 [Globalizing Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)