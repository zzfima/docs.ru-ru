---
title: "Практическое руководство. Отслеживание изменения атрибутов форматирования текста в элементе управления RichTextBox в Windows Forms | Microsoft Docs"
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
  - "примеры [Windows Forms], текстовые поля"
  - "RichTextBox - элемент управления [Windows Forms], определение изменения шрифтов"
  - "SelBold - свойство"
  - "SelChange - событие"
  - "текстовые поля, определение изменения шрифтов"
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Отслеживание изменения атрибутов форматирования текста в элементе управления RichTextBox в Windows Forms
Как правило, элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> используется для форматирования текста с применением таких атрибутов, как параметры шрифта или стиль абзаца.  В приложениях часто требуется отслеживать изменения формата текста, чтобы учитывать их при отображении панели инструментов, как это делается во многих текстовых редакторах.  
  
### Чтобы реагировать на изменения атрибутов форматирования, выполните следующие действия:  
  
1.  Добавьте в обработчик событий <xref:System.Windows.Forms.RichTextBox.SelectionChanged> код, выполняющий определенные действия в зависимости от значения атрибута.  В приведенном ниже примере вид кнопки панели инструментов изменяется в зависимости от значения свойства <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>.  Кнопка панели инструментов изменится только после перемещения курсора внутри элемента управления.  
  
     В этом примере предполагается наличие формы с элементом управления <xref:System.Windows.Forms.RichTextBox> и элементом управления <xref:System.Windows.Forms.ToolBar>, содержащим кнопку.  Дополнительные сведения о панелях инструментов и их кнопках см. в разделе [Практическое руководство. Добавление кнопок в элемент управления ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>   
 <xref:System.Windows.Forms.RichTextBox>   
 [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)