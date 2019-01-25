---
title: Как выполнить Определить, при форматировании изменение атрибутов элемента управления RichTextBox в Windows Forms
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
ms.openlocfilehash: e746cd1d0f9f7d9850d0263ee6ed0a82472fcb5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504162"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Как выполнить Определить, при форматировании изменение атрибутов элемента управления RichTextBox в Windows Forms
Обычно используются в Windows Forms <xref:System.Windows.Forms.RichTextBox> управления используется для форматирования текста с помощью атрибутов, таких как параметры шрифт или стиль абзаца. Приложение может потребоваться для отслеживания изменений в целях отображения панели инструментов, как и множество текстовых приложений форматирования текста.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Реагировать на изменения атрибутов форматирования  
  
1.  Написание кода в <xref:System.Windows.Forms.RichTextBox.SelectionChanged> обработчик событий может выполнять соответствующие действия в зависимости от значения атрибута. В следующем примере изменяется внешний вид кнопки на панели инструментов в зависимости от значения <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> свойство. Кнопки панели инструментов будут обновлены только в том случае, когда курсор перемещается в элементе управления.  
  
     В приведенном ниже примере предполагается, что форма <xref:System.Windows.Forms.RichTextBox> управления и <xref:System.Windows.Forms.ToolBar> элемент управления, содержащий кнопку панели инструментов. Дополнительные сведения о панели инструментов и кнопки панели инструментов, см. в разделе [как: Добавление кнопок в элемент управления ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
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
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
