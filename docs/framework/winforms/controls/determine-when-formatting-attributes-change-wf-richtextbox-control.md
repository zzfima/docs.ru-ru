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
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="8df7a-102">Практическое руководство. Отслеживание изменения атрибутов форматирования текста в элементе управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8df7a-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="8df7a-103">Общее использование управления формами <xref:System.Windows.Forms.RichTextBox> Windows — это форматирование текста с такими атрибутами, как параметры шрифта или стили абзацев.</span><span class="sxs-lookup"><span data-stu-id="8df7a-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="8df7a-104">Возможно, вашему приложению придется отслеживать любые изменения в форматировании текста с целью отображения панели инструментов, как во многих приложениях для обработки слов.</span><span class="sxs-lookup"><span data-stu-id="8df7a-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="8df7a-105">Реагировать на изменения в атрибутах форматирования</span><span class="sxs-lookup"><span data-stu-id="8df7a-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="8df7a-106">Напишите код <xref:System.Windows.Forms.RichTextBox.SelectionChanged> в обработчике событий для выполнения соответствующего действия в зависимости от значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="8df7a-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="8df7a-107">Следующий пример изменяет внешний вид кнопки панели <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> инструментов в зависимости от значения свойства.</span><span class="sxs-lookup"><span data-stu-id="8df7a-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="8df7a-108">Кнопка панели инструментов будет обновляться только при перемещении точки вставки в элемент управления.</span><span class="sxs-lookup"><span data-stu-id="8df7a-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="8df7a-109">Приведенный ниже пример предполагает <xref:System.Windows.Forms.RichTextBox> форму с <xref:System.Windows.Forms.ToolBar> элементом управления и элементом управления, содержащим кнопку панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="8df7a-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="8df7a-110">Для получения дополнительной [информации](how-to-add-buttons-to-a-toolbar-control.md)о панели инструментов и кнопки панели инструментов, см.</span><span class="sxs-lookup"><span data-stu-id="8df7a-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8df7a-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8df7a-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="8df7a-112">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8df7a-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="8df7a-113">Элементы управления для использования в формах Windows</span><span class="sxs-lookup"><span data-stu-id="8df7a-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
