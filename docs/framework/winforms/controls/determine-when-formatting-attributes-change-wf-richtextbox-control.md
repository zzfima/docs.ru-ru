---
title: Определите, когда изменение атрибутов форматирования в управлении RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142268"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Практическое руководство. Отслеживание изменения атрибутов форматирования текста в элементе управления RichTextBox в Windows Forms
Общее использование управления формами <xref:System.Windows.Forms.RichTextBox> Windows — это форматирование текста с такими атрибутами, как параметры шрифта или стили абзацев. Возможно, вашему приложению придется отслеживать любые изменения в форматировании текста с целью отображения панели инструментов, как во многих приложениях для обработки слов.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Реагировать на изменения в атрибутах форматирования  
  
1. Напишите код <xref:System.Windows.Forms.RichTextBox.SelectionChanged> в обработчике событий для выполнения соответствующего действия в зависимости от значения атрибута. Следующий пример изменяет внешний вид кнопки панели <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> инструментов в зависимости от значения свойства. Кнопка панели инструментов будет обновляться только при перемещении точки вставки в элемент управления.  
  
     Приведенный ниже пример предполагает <xref:System.Windows.Forms.RichTextBox> форму с <xref:System.Windows.Forms.ToolBar> элементом управления и элементом управления, содержащим кнопку панели инструментов. Для получения дополнительной [информации](how-to-add-buttons-to-a-toolbar-control.md)о панели инструментов и кнопки панели инструментов, см.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в формах Windows](controls-to-use-on-windows-forms.md)
